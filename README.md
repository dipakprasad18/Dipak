#include <stdio.h>
void bubbleSort(int matrix[][4], int rows, int cols) {
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols - 1; j++) {
            for (int k = 0; k < cols - j - 1; k++) {
                if (matrix[i][k] > matrix[i][k + 1]) {
                    int temp = matrix[i][k];
                    matrix[i][k] = matrix[i][k + 1];
                    matrix[i][k + 1] = temp;
                }
            }
        }
    }
}
int main() {
    int rows, cols;
    printf("Enter the number of rows: ");
    scanf("%d", &rows);
    int main() {
    int rows, cols;
    printf("Enter the number of rows: ");
    scanf("%d", &rows);
    printf("Enter the number of columns: ");
    scanf("%d", &cols);
    int matrix[rows][cols];
    printf("Enter the elements of the matrix:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }

    int target; 
    printf("Enter the target value to search for: ");
    scanf("%d", &target);
    int left = 0, right = rows * cols - 1;
    int found = 0; 
    while (left <= right) {
        int mid = left + (right - left) / 2;
        int midValue = matrix[mid / cols][mid % cols]; 
        if (midValue == target) {
            found = 1; 
            break; 
        } else if (midValue < target) {
            left = mid + 1; 
        } else {
            right = mid - 1;
        }
    }
    if (found) {
        printf("Target %d was found in the matrix.\n", target);
    } else {
        printf("Target %d was not found in the matrix.\n", target);
    }

    return 0;
}