#include <stdio.h>

int main() {
    int n, i, j;
    printf("Enter the number of integers in the list: ");
    scanf("%d", &n);

    int arr[n];
    printf("Enter the integers separated by spaces: ");
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    printf("Minimum and Maximum value sequences for each number in the list:\n");
    for (i = 0; i < n; i++) {
        int min = arr[i], max = arr[i];
        for (j = 0; j < n; j++) {
            if (arr[j] < min) {
                min = arr[j];
            }
            if (arr[j] > max) {
                max = arr[j];
            }
        }
        printf("%d: %d %d\n", arr[i], min, max);
    }

    return 0;
}
