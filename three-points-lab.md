/*
    Title:      Lab 1 – threepoints.cpp
    Purpose:    read three points and determine if they form a line or triangle
    Author:     Richard Lung Wicaksono
    Date:       October 27, 2019
*/

#include <iostream>
#include <iomanip>
#include <cmath>

using std::cout;
using std::cin;
using std::endl;
using std::setw;
using std::setprecision;
using std::fixed;
using std::max;
using std::min;

double Slope(double, double, double, double);
double Length(double, double, double, double);
double Area(double, double, double);
double Perimeter(double, double, double);
double Angle(double, double, double);


int main() {
    double xVal, yVal;
    double x1, y1, x2, y2, x3, y3;
    double sideA, sideB, sideC;
    double minX, minY, maxX, maxY;
    const double PI = 3.14159;
    //Prints out the input points and prompts the user for three
    //different coordinates
    for (int i = 1; i <= 3; i++) {
        cout << "Input Point " << i << ": ";
        cin >> xVal >> yVal;
        //Assigns the inputs above to their respective variables
        if (i == 1) {
            x1 = xVal;
            y1 = yVal;
        } else if (i == 2) {
            x2 = xVal;
            y2 = yVal;
        } else {
            x3 = xVal;
            y3 = yVal;
        }
    }
    //Finds the minimum and maximum coordinates in order to find the
    //endpoints of a line
    minX = min(min(x1, x2), x3);
    minY = min(min(y1, y2), y3);
    maxX = max(max(x1, x2), x3);
    maxY = max(max(y1, y2), y3);
    //Finds the sides of a triangle using the Length() function
    sideA = Length(x1, y1, x2, y2);
    sideB = Length(x2, y2, x3, y3);
    sideC = Length(x1, y1, x3, y3);
    //
    if (x1 == x2 || x2 == x3 || x1 == x3) {
        cout << "Infinite Slope" << endl;
    } else if (y1 == y2 || y2 == y3 || y1 == y3) {
        cout << "A Triangle" << endl;
        cout << "Sides: " << endl;
        cout << setw(6) << setprecision(2) << fixed << sideA << endl;
        cout << setw(6) << setprecision(2) << fixed << sideB << endl;
        cout << setw(6) << setprecision(2) << fixed << sideC << endl;

        cout << "Angles: " << endl;
        cout << setw(6) << setprecision(2) << fixed << Angle(sideA, sideB, sideC)
             << " rad, " << Angle(sideA, sideB, sideC) * 180 / PI << " degrees" << endl;

        cout << setw(6) << setprecision(2) << fixed << Angle(sideB, sideA, sideC)
                << " rad, " << Angle(sideB, sideA, sideC) * 180 / PI << " degrees" << endl;

        cout << setw(6) << setprecision(2) << fixed << Angle(sideC, sideB, sideA)
             << " rad, " << Angle(sideC, sideB, sideA) * 180 / PI << " degrees" << endl;


        cout << "Perimeter: " << setw(6) << setprecision(2) << fixed << Perimeter(sideA, sideB, sideC) << endl;
        cout << "Area: " << setw(11) << setprecision(2) << fixed << Area(sideA, sideB, sideC) << endl;
    } else {
        cout << "A Line" << endl;
        cout << "Slope: " << setw(7) << setprecision(2) << fixed << Slope(x1, y1, x2, y2) << endl;
        cout << "Length: " << setw(6) << setprecision(2) << fixed << Length(minX, minY, maxX, maxY) << endl;
    }


    return 0;
}
// Calculates the slope of the line
// Params: four doubles that represent two of the coordinates of the line
// Returns: a double, the slope of the line
// Format Error: there should be no errors
double Slope(double x1, double y1, double x2, double y2) {
    double slopeVal;

    slopeVal = (y2 - y1) / (x2 - x1);

    return slopeVal;
}
// Calculates the length of the line
// Params: four doubles that represent the endpoints of the line
// Returns: a double, the length of the line
// Format Error: there should be no errors
double Length(double x1, double y1, double x2, double y2) {
    double lengthVal;

    lengthVal = sqrt(pow(x2 - x1, 2.0) + pow(y2 - y1, 2.0));

    return lengthVal;
}
// Calculates the area of the triangle
// Params: three doubles that represent the length of each of the triangles
// sides
// Returns: a double, the area of the sides
// Format Error: there should be no errors
double Area(double sideA, double sideB, double sideC) {
    double semiPerim;
    double areaVal;

    semiPerim = (sideA + sideB + sideC) / 2;
    areaVal = sqrt(semiPerim * (semiPerim - sideA) * (semiPerim - sideB) * (semiPerim - sideC));

    return areaVal;
}
// Calculates the perimeter of the triangle
// Params: three doubles that represent the length of each of the triangles
// sides
// Returns: a double, the perimeter of the sides
// Format Error: there should be no errors
double Perimeter(double sideA, double sideB, double sideC){
    double perimeterVal;

    perimeterVal = sideA + sideB + sideC;

    return perimeterVal;
}
// Calculates the interior angles of the triangle
// Params: three doubles that represent the length of each of the triangles
// sides
// Returns: a double, the angle of the sides
// Format Error: there should be no errors
double Angle(double sideA, double sideB, double sideC) {
    double angleVal;

    angleVal = acos((pow(sideB, 2.0) + pow(sideC, 2.0) - pow(sideA, 2.0)) / (2 * sideB * sideC));

    return angleVal;
}
