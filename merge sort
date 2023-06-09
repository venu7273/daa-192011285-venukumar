#include <stdio.h>
void merging(int low, int mid, int high, int a[], int b[]) {
   int l1, l2, i;
   for (l1 = low, l2 = mid + 1, i = low; l1 <= mid && l2 <= high; i++) {
      if (a[l1] <= a[l2])
         b[i] = a[l1++];
      else
         b[i] = a[l2++];
   }
   while (l1 <= mid)    
      b[i++] = a[l1++];
   while (l2 <= high)   
      b[i++] = a[l2++];
   for (i = low; i <= high; i++)
      a[i] = b[i];
}
void sort(int low, int high, int a[], int b[]) {
   int mid;  
   if (low < high) {
      mid = (low + high) / 2;
      sort(low, mid, a, b);
      sort(mid + 1, high, a, b);
      merging(low, mid, high, a, b);
   }   
}
int main() { 
   int n, i;
   printf("Enter the number of elements: ");
   scanf("%d", &n);
   int a[n], b[n];
   printf("Enter %d elements to sort:\n", n);
   for (i = 0; i < n; i++)
      scanf("%d", &a[i]);
   printf("\nList before sorting:\n");
   for (i = 0; i < n; i++)
      printf("%d ", a[i]);
   sort(0, n - 1, a, b);
   printf("\nList after sorting:\n");
   for (i = 0; i < n; i++)
      printf("%d ", a[i]);
   printf("\n");
   return 0;
}
