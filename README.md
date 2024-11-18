# BucketSort

Ejercicio de bucket sort en python 
´´ python 

def bucket_sort(arr):
    n = len(arr)
    
    # Crear n "buckets" vacíos
    buckets = [[] for _ in range(n)]

    # Distribuir los elementos en los buckets
    for i in range(n):
        bi = int(n * arr[i])  # Calculamos el índice del bucket
        buckets[bi].append(arr[i])

    # Ordenar cada bucket
    for i in range(n):
        buckets[i].sort()

    # Reconstruir el arreglo original con los elementos ordenados
    index = 0
    for i in range(n):
        for j in range(len(buckets[i])):
            arr[index] = buckets[i][j]
            index += 1

# Ejemplo de uso
arr = [0.42, 0.32, 0.56, 0.23, 0.75, 0.12, 0.24, 0.56]
bucket_sort(arr)
print("Arreglo ordenado:", arr)


´´
