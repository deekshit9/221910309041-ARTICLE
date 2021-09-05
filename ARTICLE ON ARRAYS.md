# C Arrays
An array is defined as the collection of similar type of data items stored at contiguous memory locations. 
___
## **How to declare an array?**

dataType arrayName[arraySize];
**for example:** 

int marks[5];

Here, we declared an array, `marks`, of floating-point type. And its size is 5. Meaning, it can hold 5 integer values.
___
## **Access Array Elements**
You can access elements of an array by indices.

Suppose you declared an array `marks` as above. The first element is `mark[0]`, the second element is `mark[1]` and so on.

* Arrays have 0 as the first index, not 1. In this example, `mark[0]` is the first element.
* If the size of an array is n, to access the last element, the `n-1` index is used.
___
## **How to initialize an array?**
It is possible to initialize an array during declaration. For example,

    int mark[5] = {19, 10, 8, 17, 9};

You can also initialize an array like this.

    int mark[] = {19, 10, 8, 17, 9};

Here, we haven't specified the size. However, the compiler knows its size is 5 as we are initializing it with 5 elements.
___
## **Change Value of Array elements**

int mark[5] = {19, 10, 8, 17, 9}

// make the value of the third element to -1

    mark[-2] = -1;

// make the value of the fifth element to 0

    mark[4] = 0;
___
## **Input and Output Array Elements**
Here's how you can take input from the user and store it in an array element.

 take input and store it in the 3rd element

​scanf("%d", &mark[2]);

take input and store it in the ith element

    scanf("%d", &mark[i-1]);

Here's how you can print an individual element of an array.

 print the first element of the array

    printf("%d", mark[0]);


 print i'th element of the array

    printf("%d", mark[i-1]);

**Program to take 5 values from the user and store them in an array.**

**Print the elements stored in the array**

    #include <stdio.h>

    int main() {
    int values[5];

    printf("Enter 5 integers: ");

    for(int i = 0; i < 5; ++i) {
        scanf("%d", &values[i]);
    }

    printf("Displaying integers: ");
    for(int i = 0; i < 5; ++i) {
        printf("%d\n", values[i]);
    }
    return 0;
    }
___    

# **Multidimensional Arrays**
In C programming, you can create an array of arrays. These arrays are known as multidimensional arrays. 

**For example,**

    int x[3][4];

Here, `x` is a two-dimensional (2d) array. The array can hold 12 elements. You can think the array as a table with `3 rows` and each row has `4 columns.`

## **Initialization of a 2d array**
    // Different ways to initialize two-dimensional array

    int c[2][3] = {{1, 3, 0}, {-1, 5, 9}};
            
    int c[][3] = {{1, 3, 0}, {-1, 5, 9}};
                    
    int c[2][3] = {1, 3, 0, -1, 5, 9};

**Example:Sum of two matrices**

// C program to find the sum of two matrices of order 2*2

    #include <stdio.h>
    int main()
    {
    float a[2][2], b[2][2], result[2][2];
    
    printf("Enter elements of 1st matrix\n");
    for (int i = 0; i < 2; ++i)
        for (int j = 0; j < 2; ++j)
        {
        printf("Enter a%d%d: ", i + 1, j + 1);
        scanf("%f", &a[i][j]);
        }

    // Taking input using nested for loop
    printf("Enter elements of 2nd matrix\n");
    for (int i = 0; i < 2; ++i)
        for (int j = 0; j < 2; ++j)
        {
        printf("Enter b%d%d: ", i + 1, j + 1);
        scanf("%f", &b[i][j]);
        }

    // adding corresponding elements of two arrays
    for (int i = 0; i < 2; ++i)
        for (int j = 0; j < 2; ++j)
        {
        result[i][j] = a[i][j] + b[i][j];
        }

    // Displaying the sum
    printf("\nSum Of Matrix:");

    for (int i = 0; i < 2; ++i)
        for (int j = 0; j < 2; ++j)
        {
        printf("%.1f\t", result[i][j]);

        if (j == 1)
            printf("\n");
        }
    return 0;
    }
Output

    Enter elements of 1st matrix
    Enter a11: 2;
    Enter a12: 0.5;
    Enter a21: -1.1;
    Enter a22: 2;
    Enter elements of 2nd matrix
    Enter b11: 0.2;
    Enter b12: 0;
    Enter b21: 0.23;
    Enter b22: 23;

    Sum Of Matrix:
    2.2     0.5
    -0.9    25.0