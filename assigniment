#include <stdio.h>

#include <stdlib.h>

#include <stdbool.h>

#define MAX_WORKERS 10

#define MAX_TASKS 10

int numWorkers, numTasks;

int costMatrix[MAX_WORKERS][MAX_TASKS];

bool assigned[MAX_WORKERS], visited[MAX_TASKS];

int assignment[MAX_WORKERS];

int minCost = 0x7FFFFFFF;  // Initialize with a large value

void inputCostMatrix() {

    printf("Enter the cost matrix (%d x %d):\n", numWorkers, numTasks);

    for (int i = 0; i < numWorkers; i++) {

        for (int j = 0; j < numTasks; j++) {

            scanf("%d", &costMatrix[i][j]);

        }

    }

}

int calculateCost() {

    int totalCost = 0;

    for (int i = 0; i < numWorkers; i++) {

        totalCost += costMatrix[i][assignment[i]];

    }

    return totalCost;

}

void branchAndBound(int worker, int cost) {

    if (worker == numWorkers) {

        if (cost < minCost) {

            minCost = cost;

        }

        return;

    }

    for (int task = 0; task < numTasks; task++) {

        if (!visited[task] && cost + costMatrix[worker][task] < minCost) {

            visited[task] = true;

            assignment[worker] = task;

            branchAndBound(worker + 1, cost + costMatrix[worker][task]);

            visited[task] = false;

        }

    }

}

void printAssignment() {

    printf("Optimal assignment:\n");

    for (int i = 0; i < numWorkers; i++) {

        printf("Worker %d -> Task %d\n", i + 1, assignment[i] + 1);

    }

}

int main() {

    printf("Enter the number of workers: ");

    scanf("%d", &numWorkers);

    printf("Enter the number of tasks: ");

    scanf("%d", &numTasks);

    if (numWorkers > MAX_WORKERS || numTasks > MAX_TASKS) {

        printf("Exceeded maximum limit of workers or tasks.\n");

        return 0;

    }

    inputCostMatrix();

    branchAndBound(0, 0);

    printf("Minimum cost: %d\n", minCost);

    printAssignment();

    return 0;

}
