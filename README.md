# BucketSort

Ejercicio de bucket sort en python.

```ruby

def bucket_sort(arr):
    n = len(arr)
    
    buckets = [[] for _ in range(n)]

    
    for i in range(n):
        bi = int(n * arr[i])  
        buckets[bi].append(arr[i])

    
    for i in range(n):
        buckets[i].sort()

    
    index = 0
    for i in range(n):
        for j in range(len(buckets[i])):
            arr[index] = buckets[i][j]
            index += 1

    arr =[0.72,0.21,0.32,0.14,0.68]
    bucket_sort = arr
    
'''
