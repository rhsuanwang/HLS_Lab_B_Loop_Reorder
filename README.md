# HLS_Lab_B_Loop_Reorder
# Algorithm
Computers usually have multiple cache layers between the processor and main memory, often called memory hierarchy. If you access the values ​​in the cache smoothly, you will end up with better performance than random access data.
In C/C++, arrays are usually stored in the row direction, which means that memory stores all values ​​adjacent to each other for each row in the matrix.
In each iteration, the value of k changes and increases. When running the innermost loop, each loop iteration will likely have a cache miss when loading B[k][j]. Every time the k increases, it will skip the entire column of the matrix and jump to a farther memory, which may exceed the value of the cache. 
![image](https://user-images.githubusercontent.com/96122960/160431175-2c2d0fdf-00a0-4dbd-89dc-075b34a2d5f8.png)
![image](https://user-images.githubusercontent.com/96122960/160431209-d474b1f8-205b-4e7a-a8eb-ee6ab84173cf.png)
Consider change the j order and k order. In each iteration, since the values ​​are in row order, the value of C[i][j] is likely to be in cache. Similarly, B[k][j] may already be cached, and since i and k have not changed, A[i][k] may also be in the cache, which means that there are cache misses in each iteration in the inner loop.
![image](https://user-images.githubusercontent.com/96122960/160431096-0d83b30a-a769-4161-9a33-62041271489e.png)
![image](https://user-images.githubusercontent.com/96122960/160431141-5d7e643a-2ad4-4500-bee4-6db455edfcfa.png)
# Code
