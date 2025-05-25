# EX 1C Quick Sort
## DATE: 25.5.2025
## AIM:
To write a python program to implement quick sort using tha last element as pivot on the list of float values.

## Algorithm
1.Select a pivot element from the array (commonly the first or last element).
2.Partition the array into two subarrays: elements less than pivot and elements greater than or equal to pivot.
3.Place the pivot between the two subarrays at its correct position.
4.Recursively apply Quick Sort to the left subarray.
5.Recursively apply Quick Sort to the right subarray.

## Program:
```
/*
Program to implement implement quick sort using the last element as pivot on the list of float values.
Developed by: Samyuktha S
Register Number: 212222240089 
*/
```
```
def partition(array, low, high):
    pivot = array[low]
    start = low + 1
    end = high
    print("pivot: ",pivot)
    while True:
        while start <= end and array[end] >= pivot:
            end = end - 1
        while start <= end and array[start] <= pivot:
            start = start + 1
        if start <= end:
            array[start], array[end] = array[end], array[start]
        else:
            break
    array[low], array[end] = array[end], array[low]
    return end
def quick_sort(array, start, end):
    if start < end:
        idx = partition(array, start, end)
        quick_sort(array, start, idx-1)
        quick_sort(array, idx+1, end)
arr1=[]
n=int(input())
for i in range(n):
    arr1.append(int(input()))
print("Input List\n",arr1)
quick_sort(arr1, 0, len(arr1)-1)
print("Sorted List\n",arr1)
```
## Output:
![image](https://github.com/user-attachments/assets/6aee89b7-c9ad-4d3a-a1b9-2582fb3c06da)

## Result:
The program successfully sorts the input array using the QuickSort algorithm, arranging the elements in ascending order.
