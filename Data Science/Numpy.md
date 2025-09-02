- scientific computing
- arrays, matrics n math fxns to operate on these math data structures
- if not installed 
	- `pip install numpy` -> in terminal/ cell
```python
import numpy as np

#create array
arr1= np.array([5,6,8,42,3,8])
arr2.reshape((1,5))            # 1 row , 5 colomns
  
arr1= np.array([1,2,5,4,8])
print(arr1)
print(type(arr1))
print(arr1.shape)
  
np.arange(0,10)
np.arange(0,10,2)
np.arange(0,10).reshape(5,2)       # 1-d to 2d array transfomation

np.ones((3,4))   # matrix of '1'
np.eye(3)        # identity matrix - dimention 3x3
arr= np.array([[1,5,6,8], [9,6,4,2]])

print(arr)
print(arr.shape)       # dimentions (rows and coloms) (2,3)
print(arr.ndim)        # dimentions (rows)  2
print(arr.size)        # no of elements 6
print(arr.dtype)       # data type of arr(differs based on system) int32
print(arr.itemsize)   #  itermsize but in bytes

# vector operations
arr1= np.array([1,5,6,8])
arr2= np.array([4,7,65,328])
  
print(arr1+arr2)        # element wise addition
print(arr1-arr2)        # return type of all these is array
print(arr1*arr2)
print(arr2//arr1)

#fxns on arrays  (element wise)
arr= np.array([1,5,6,8])
print(np.sqrt(arr))         # return type is arra
print(np.exp(arr))          # e raised to power of element of array
print(np.sin(arr))
print(np.log(arr))

```
### some differences
In Python, particularly within the context of NumPy arrays or Pandas Series/DataFrames, `size` and `itemsize` represent distinct attributes related to data dimensions and memory allocation.

- `size`: This attribute returns the total number of elements in the array or data structure. For a 1D array or Series, it is simply the number of elements. For a 2D array or DataFrame, it is the product of the number of rows and the number of columns.

Python

```python
    import numpy as np 
       arr_1d = np.array([1, 2, 3])   
     print(f"Size of 1D array: {arr_1d.size}") # Output: 3    
     arr_2d = np.array([[1, 2], [3, 4]])    
     print(f"Size of 2D array: {arr_2d.size}") # Output: 4
```

- `itemsize`: This attribute returns the size in bytes of a single element within the array or data structure. This size is determined by the data type (`dtype`) of the elements. For instance, an `int64` element will have an `itemsize` of 8 bytes, while an `int32` element will have an `itemsize` of 4 bytes. 

Python

```python
    import numpy as np   
     arr_int64 = np.array([1, 2, 3], dtype=np.int64)    
     print(f"Itemsize of int64 array: {arr_int64.itemsize}") # Output: 8    
     arr_int32 = np.array([1, 2, 3], dtype=np.int32)   
      print(f"Itemsize of int32 array: {arr_int32.itemsize}") # Output: 4
```

In summary, `size` tells you how many individual data points are present, while `itemsize` tells you how much memory each of those individual data points occupies. The total memory consumed by the array can be calculated as `size * itemsize`.

## 📐 Array Shape & Structure

|Attribute / Method|Description|
|---|---|
|`arr.shape`|Tuple of array dimensions|
|`arr.ndim`|Number of dimensions|
|`arr.size`|Total number of elements|
|`arr.dtype`|Data type of elements|
|`arr.itemsize`|Size in bytes of one element|
|`arr.nbytes`|Total memory (bytes) used|
|`arr.T`|Transpose of the array|
|`arr.reshape()`|Reshape the array|
|`arr.ravel()`|Flatten the array (view)|
|`arr.flatten()`|Flatten the array (copy)|

---

## 🧪 Array Creation

|Function|Description|
|---|---|
|`np.array()`|Create array from list or tuple|
|`np.zeros()`|Array of all zeros|
|`np.ones()`|Array of all ones|
|`np.empty()`|Uninitialized array|
|`np.full(shape, val)`|Array filled with a constant value|
|`np.eye()`|Identity matrix|
|`np.arange(start, stop)`|Array with range of values|
|`np.linspace(start, stop, num)`|Evenly spaced values|
|`np.random.rand()`|Random float values|
|`np.random.randint()`|Random integers|

---

## 🔁 Array Manipulation

|Method|Description|
|---|---|
|`arr.copy()`|Returns a copy of the array|
|`arr.astype(dtype)`|Change data type|
|`np.concatenate()`|Join arrays along an axis|
|`np.stack()`|Stack arrays along new axis|
|`np.split()`|Split array into sub-arrays|
|`np.hstack()`|Stack horizontally|
|`np.vstack()`|Stack vertically|
|`np.append()`|Append values to array|
|`np.insert()`|Insert values into array|
|`np.delete()`|Delete values from array|

---

## 🔍 Indexing & Searching

|Method|Description|
|---|---|
|`np.where(condition)`|Indices where condition is True|
|`np.argmax()`|Index of max element|
|`np.argmin()`|Index of min element|
|`np.nonzero()`|Indices of non-zero elements|
|`np.unique()`|Sorted unique values of array|

---

## 📊 Math & Statistics

|Method|Description|
|---|---|
|`arr.sum()`|Sum of array elements|
|`arr.mean()`|Mean value|
|`arr.std()`|Standard deviation|
|`arr.var()`|Variance|
|`arr.min()`|Minimum value|
|`arr.max()`|Maximum value|
|`arr.cumsum()`|Cumulative sum|
|`arr.cumprod()`|Cumulative product|
|`np.percentile()`|Percentile|
|`np.median()`|Median value|

---

## 🧮 Element-wise Operations

|Function|Description|
|---|---|
|`np.add()`|Element-wise addition|
|`np.subtract()`|Element-wise subtraction|
|`np.multiply()`|Element-wise multiplication|
|`np.divide()`|Element-wise division|
|`np.power()`|Raise elements to power|
|`np.mod()`|Modulo operation|
|`np.sqrt()`|Square root|
|`np.exp()`|Exponential|
|`np.log()`|Natural logarithm|

---

## 🧼 Cleaning & Checking

|Function|Description|
|---|---|
|`np.isnan()`|Check for NaN values|
|`np.isinf()`|Check for infinite values|
|`np.isfinite()`|Check for finite values|
