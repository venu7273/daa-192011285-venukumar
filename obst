#include <stdio.h>
#include <stdlib.h>
#include <limits.h>

// Function to calculate the cost of a sub-tree
int calculate_cost(int freq[], int i, int j) {
    int k;
    int sum = 0;
    for (k = i; k <= j; k++) {
        sum += freq[k];
    }
    return sum;
}

// Function to find the optimal binary search tree using dynamic programming
void optimal_bst(int keys[], int freq[], int n) {
    int cost[n][n];
    int i, j, k, l, r;
 
    // Initialize cost matrix
    for (i = 0; i < n; i++) {
        cost[i][i] = freq[i];
    }
 
    // Calculate cost of sub-trees
    for (l = 2; l <= n; l++) {
        for (i = 0; i <= n-l+1; i++) {
            j = i + l - 1;
            cost[i][j] = INT_MAX;
            for (k = i; k <= j; k++) {
                r = ((k > i) ? cost[i][k-1] : 0) + 
                    ((k < j) ? cost[k+1][j] : 0) + 
                    calculate_cost(freq, i, j);
                if (r < cost[i][j]) {
                    cost[i][j] = r;
                }
            }
        }
    }
 
    // Print the minimum cost
    printf("Minimum cost = %d\n", cost[0][n-1]);
}

int main() {
    int n, i;
    printf("Enter the number of keys: ");
    scanf("%d", &n);
    int keys[n], freq[n];
    printf("Enter the keys and frequencies:\n");
    for (i = 0; i < n; i++) {
        scanf("%d %d", &keys[i], &freq[i]);
    }
    optimal_bst(keys, freq, n);
    return 0;
}
