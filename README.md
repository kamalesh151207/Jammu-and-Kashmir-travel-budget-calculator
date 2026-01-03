# Jammu-and-Kashmir-travel-budget-calculator
#include <stdio.h>

struct Travel {
    int persons, days;
    int transportChoice, hotelChoice, sightChoice, foodChoice;
    double transportCost, hotelCost, foodCost, sightseeingCost, totalCost;
};

int main() {
    struct Travel t;

    printf("====== Jammu & Kashmir Travel Budget Calculator ======");

    printf("\nEnter number of persons: ");
    scanf("%d", &t.persons);
    if (t.persons <= 0) {
        printf("\nInvalid number of persons!");
        return 0;
    }

    printf("\nEnter number of days: ");
    scanf("%d", &t.days);
    if (t.days <= 0) {
        printf("\nInvalid number of days!");
        return 0;
    }

    /* Transport */
    printf("\nSelect Transport Mode");
    printf("\n1. Train  (₹2000 per person)");
    printf("\n2. Bus    (₹1500 per person)");
    printf("\n3. Flight (₹6000 per person)");
    printf("\nEnter choice: ");
    scanf("%d", &t.transportChoice);

    if (t.transportChoice == 1)
        t.transportCost = t.persons * 2000.0;
    else if (t.transportChoice == 2)
        t.transportCost = t.persons * 1500.0;
    else if (t.transportChoice == 3)
        t.transportCost = t.persons * 6000.0;
    else {
        printf("\nInvalid Transport Choice!");
        return 0;
    }

    /* Hotel */
    printf("\nSelect Accommodation Type");
    printf("\n1. Budget Hotel   (₹1000 per day)");
    printf("\n2. Standard Hotel (₹2500 per day)");
    printf("\n3. Luxury Hotel   (₹5000 per day)");
    printf("\nEnter choice: ");
    scanf("%d", &t.hotelChoice);

    if (t.hotelChoice == 1)
        t.hotelCost = t.days * 1000.0;
    else if (t.hotelChoice == 2)
        t.hotelCost = t.days * 2500.0;
    else if (t.hotelChoice == 3)
        t.hotelCost = t.days * 5000.0;
    else {
        printf("\nInvalid Hotel Choice!");
        return 0;
    }

    /* Food Preference */
    printf("\nSelect Food Preference");
    printf("\n1. Veg     (₹400 per person per day)");
    printf("\n2. Non-Veg (₹600 per person per day)");
    printf("\n3. Mixed   (₹500 per person per day)");
    printf("\nEnter choice: ");
    scanf("%d", &t.foodChoice);

    if (t.foodChoice == 1)
        t.foodCost = t.persons * t.days * 400.0;
    else if (t.foodChoice == 2)
        t.foodCost = t.persons * t.days * 600.0;
    else if (t.foodChoice == 3)
        t.foodCost = t.persons * t.days * 500.0;
    else {
        printf("\nInvalid Food Choice!");
        return 0;
    }

    /* Sightseeing */
    printf("\nDo you want Sightseeing Package?");
    printf("\n1. Yes (₹3000 per person)");
    printf("\n2. No");
    printf("\nEnter choice: ");
    scanf("%d", &t.sightChoice);

    if (t.sightChoice == 1)
        t.sightseeingCost = t.persons * 3000.0;
    else if (t.sightChoice == 2)
        t.sightseeingCost = 0.0;
    else {
        printf("\nInvalid Sightseeing Choice!");
        return 0;
    }

    /* Total */
    t.totalCost = t.transportCost + t.hotelCost + t.foodCost + t.sightseeingCost;

    printf("\n----------- Cost Breakdown -----------");
    printf("\nTransport Cost     : ₹%.2lf", t.transportCost);
    printf("\nHotel Cost         : ₹%.2lf", t.hotelCost);
    printf("\nFood Cost          : ₹%.2lf", t.foodCost);
    printf("\nSightseeing Cost   : ₹%.2lf", t.sightseeingCost);
    printf("\n-------------------------------------");
    printf("\nTotal Trip Cost    : ₹%.2lf", t.totalCost);

    return 0;
}
