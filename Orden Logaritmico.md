

```python
# Función para determinar si existe un `target` en la lista ordenada `num'
# o no usando un algoritmo de búsqueda binaria
# Supongamos que tenemos el siguiente arreglo:
#                0, 1, 2, 3, 4, 5,  6,  7,  8 
#           a = [2, 5, 6, 8, 9, 10, 13, 14, 17]
# y queremos encontrar el numero 2
#                 
def binarySearch(nums, target):
# 0 #  0,8    0     9 - 1
    (left, right) = (0, len(nums) - 1)
#i=0,0<=8 #
#i=1,0<=3 #
#i=2,0<=0 #
    while left <= right:
#i=0,4=(0 + 8)/2
#i=1,1=(0+3)/2
#i=2,0=(0+0)/2
        mid = (left + right) // 
#i=0,2==nums[4]=9?false
#i=1,2==nums[1]=5?false
#i=2,2==nums[0]=2?true
        if target == nums[mid]:
            return mid
#i=0,2<nums[4]=9?true
#i=1,2<nums[1]=5?true
        elif target < nums[mid]:
#i=0,3=4-1
#i=1,0=1-1
            right = mid - 1
        else:
            left = mid + 1
    return -1
```

Implementacion recursiva:
```python

def binarySearch(nums, left, right, target):
    if left > right:
        return -1
    mid = (left + right) // 2
    if target == nums[mid]:
        return mid
    elif target < nums[mid]:
        return binarySearch(nums, left, mid - 1, target)
    else:
        return binarySearch(nums, mid + 1, right, target)

```