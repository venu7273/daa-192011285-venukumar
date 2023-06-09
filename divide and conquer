#include <stdio.h>
void findMaxMin(int arr[], int start, int end, int *max, int *min) {
    int mid, max1, max2, min1, min2;
    if (start == end) {
        *max = arr[start];
        *min = arr[start];
    }
    else if (end == start + 1) {
        if (arr[start] > arr[end]) {
            *max = arr[start];
            *min = arr[end];
        }
        else {
            *max = arr[end];
            *min = arr[start];
        }
    }
    else {
        mid = (start + end) / 2;
        findMaxMin(arr, start, mid, &max1, &min1);
        findMaxMin(arr, mid+1, end, &max2, &min2);
        
        if (max1 > max2) {
            *max = max1;
        }
        else {
            *max = max2;
        }
        
        if (min1 < min2) {
            *min = min1;
        }
        else {
            *min = min2;
        }
    }
}

int main() {
    int arr[100], n, max, min, i;
    
    printf("Enter the number of elements in the array: ");
    scanf("%d", &n);
    
    printf("Enter the elements of the array: ");
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    findMaxMin(arr, 0, n-1, &max, &min);
    
    printf("Maximum value in the array: %d\n", max);
    printf("Minimum value in the array: %d\n", min);
    
    return 0;
}
