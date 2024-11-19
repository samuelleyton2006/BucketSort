# BucketSort

Ejercicio de bucket sort en python.

```python 

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

```


Implementacion Java 

```java
import java.util.ArrayList;
import java.util.Collections;

public class Main {
    public static void bucketSort(int[] arr) {
        // 1. Encontrar el valor máximo en el arreglo
        int maxValue = Integer.MIN_VALUE;
        for (int num : arr) {
            if (num > maxValue) {
                maxValue = num;
            }
        }

        // 2. Crear los buckets
        int bucketCount = maxValue / 10 + 1; // Puedes ajustar el tamaño del bucket
        ArrayList<ArrayList<Integer>> buckets = new ArrayList<>(bucketCount);
        
        for (int i = 0; i < bucketCount; i++) {
            buckets.add(new ArrayList<>());
        }

        // 3. Distribuir los elementos en los buckets
        for (int num : arr) {
            int bucketIndex = num / 10; // Asignar a un bucket basado en el valor
            buckets.get(bucketIndex).add(num);
        }

        // 4. Ordenar cada bucket y concatenar los resultados
        int index = 0;
        for (ArrayList<Integer> bucket : buckets) {
            Collections.sort(bucket); // Ordenar cada bucket
            for (int num : bucket) {
                arr[index++] = num; // Concatenar los resultados en el arreglo original
            }
        }
    }

    public static void main(String[] args) {
        int[] arr = {34, 2, 10, 6, 7, 5, 12, 3};
        
        System.out.println("Arreglo original:");
        for (int num : arr) {
            System.out.print(num + " ");
        }
        
        bucketSort(arr);
        
        System.out.println("\nArreglo ordenado:");
        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
}

```



java 2 

```java

import java.util.ArrayList;
import java.util.Collections;

public class Main  {
    public static void bucketSort(int[] arr) {
        if (arr.length == 0) return; // Verificar si el arreglo está vacío

        // 1. Encontrar el valor máximo y mínimo en el arreglo
        int maxValue = Integer.MIN_VALUE;
        int minValue = Integer.MAX_VALUE;
        for (int num : arr) {
            if (num > maxValue) {
                maxValue = num;
            }
            if (num < minValue) {
                minValue = num;
            }
        }

        // 2. Crear los buckets
        int bucketCount = (maxValue - minValue) / 10 + 1; // Ajustar según el rango
        ArrayList<ArrayList<Integer>> buckets = new ArrayList<>(bucketCount);
        
        for (int i = 0; i < bucketCount; i++) {
            buckets.add(new ArrayList<>());
        }

        // 3. Distribuir los elementos en los buckets
        for (int num : arr) {
            int bucketIndex = (num - minValue) / 10; // Asignar a un bucket basado en el valor ajustado
            buckets.get(bucketIndex).add(num);
        }

        // 4. Ordenar cada bucket y concatenar los resultados
        int index = 0;
        for (ArrayList<Integer> bucket : buckets) {
            Collections.sort(bucket); // Ordenar cada bucket
            for (int num : bucket) {
                arr[index++] = num; // Concatenar los resultados en el arreglo original
            }
        }
    }

    public static void main(String[] args) {
        int[] arr = {34, -2, 10, -6, 7, 5, 12, 3};
        
        System.out.println("Arreglo original:");
        for (int num : arr) {
            System.out.print(num + " ");
        }
        
        bucketSort(arr);
        
        System.out.println("\nArreglo ordenado:");
        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
}


```

implementacion enteros en python 

```python

def bucket_sort(arr):
    if len(arr) == 0:
        return arr

    # Encontrar el valor máximo y mínimo en el arreglo
    max_value = max(arr)
    min_value = min(arr)

    # Crear los buckets
    bucket_count = (max_value - min_value) // 10 + 1
    buckets = [[] for _ in range(bucket_count)]

    # Distribuir los elementos en los buckets
    for num in arr:
        bucket_index = (num - min_value) // 10
        buckets[bucket_index].append(num)

    # Ordenar cada bucket y concatenar los resultados
    sorted_arr = []
    for bucket in buckets:
        sorted_arr.extend(sorted(bucket))  # Ordenar cada bucket y agregar al resultado

    return sorted_arr

# Ejemplo de uso
if __name__ == "__main__":
    arr = [34, -2, 10, -6, 7, 5, 12, 3]
    
    print("Arreglo original:")
    print(arr)
    
    sorted_arr = bucket_sort(arr)
    
    print("Arreglo ordenado:")
    print(sorted_arr)
```


    
