#include <iostream>

using namespace std;

void getArray(int a[], int n) {
    cout << "Enter values for the array: ";
    for (int i = 0; i < n; i++) {
        cin >> a[i];
    }
}

void printArray(int a[], int n) {
    cout << "Array elements: ";
    for (int i = 0; i < n; i++) {
        cout << a[i] << " ";
    }
    cout << endl;
}

int find_maxindex(int a[], int n) {
    int maxIndex = 0;
    int maxValue = a[0];
    for (int i = 1; i < n; i++) {
        if (a[i] > maxValue) {
            maxValue = a[i];
            maxIndex = i;
        }
    }
    return maxIndex;
}

void find_max(int a[], int n, int &maxvalue, int &maxindex) {
    maxindex = 0;
    maxvalue = a[0];
    for (int i = 1; i < n; i++) {
        if (a[i] > maxvalue) {
            maxvalue = a[i];
            maxindex = i;
        }
    }
}

void sum_avg(int a[], int n, int &sum, float &avg) {
    sum = 0;
    for (int i = 0; i < n; i++) {
        sum += a[i];
    }
    avg = static_cast<float>(sum) / n;  // Ensure accurate float division
}

int main() {
    int n;
    cout << "Enter the size of the array: ";
    cin >> n;

    int a[n];  // Dynamically allocate memory for the array

    getArray(a, n);
    printArray(a, n);

    int maxIndex, maxValue;
    find_maxindex(a, n);  // Use the more efficient `find_maxindex`

    cout << "The maximum value in the array is " << maxValue << " at index " << maxIndex << endl;

    int sum;
    float avg;
    sum_avg(a, n, sum, avg);

    cout << "The sum of the elements is " << sum << endl;
    cout << "The average of the elements is " << avg << endl;

    return 0;
}
