# HLS_Lab_B_Loop_Reorder
# Algorithm
Computers usually have multiple cache layers between the processor and main memory, often called memory hierarchy. If you access the values ​​in the cache smoothly, you will end up with better performance than random access data.
In C/C++, arrays are usually stored in the row direction, which means that memory stores all values ​​adjacent to each other for each row in the matrix.
In each iteration, the value of k changes and increases. When running the innermost loop, each loop iteration will likely have a cache miss when loading B[k][j]. Every time the k increases, it will skip the entire column of the matrix and jump to a farther memory, which may exceed the value of the cache. 
![image](https://user-images.githubusercontent.com/96122960/160426726-08bcae67-f75e-43b2-998b-10b5f5905820.png)
![image](https://user-images.githubusercontent.com/96122960/160426911-acad2cba-d979-4989-8558-e053999ba149.png)
Consider change the j order and k order. In each iteration, since the values ​​are in row order, the value of C[i][j] is likely to be in cache. Similarly, B[k][j] may already be cached, and since i and k have not changed, A[i][k] may also be in the cache, which means that there are cache misses in each iteration in the inner loop.
![image](https://user-images.githubusercontent.com/96122960/160430726-f78bda34-25e9-4fed-b9a3-84ed848446ef.png)
![image](https://user-images.githubusercontent.com/96122960/160430755-45d2bb79-2305-47a3-bc54-9396b8103758.png)
# Code
