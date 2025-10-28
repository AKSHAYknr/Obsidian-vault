
---
A **tensor** is a **multidimensional array** — basically a generalization of scalars, vectors, and matrices to any number of dimensions.

It’s the **core data structure** used in ML frameworks like **TensorFlow**, **PyTorch**, and **NumPy**.

---

## 📏 **Tensor Basics**

| Type       | Example                              | Dimensions (Rank) | Description                                  |
| ---------- | ------------------------------------ | ----------------- | -------------------------------------------- |
| **Scalar** | 5                                    | 0D                | Single number (no direction, no axis)        |
| **Vector** | [1, 2, 3]                            | 1D                | Array of numbers (1 axis)                    |
| **Matrix** | [[1, 2], [3, 4]]                     | 2D                | 2D array (rows × columns)                    |
| **Tensor** | [[[1, 2], [3, 4]], [[5, 6], [7, 8]]] | 3D+               | Multidimensional array (can be 3D, 4D, etc.) |

---

## 🧩 **Examples in ML Context**

- **0D (Scalar):**  
    A single weight value in a model → `w = 0.25`
    
- **1D (Vector):**  
    A list of weights → `[0.2, 0.5, 0.7]`
    
- **2D (Matrix):**  
    A layer’s weight connections between input and output neurons  
    e.g.
    
    `[[0.2, 0.8],  [0.5, 0.1],  [0.9, 0.4]]`
    
- **3D Tensor:**  
    A batch of images represented as (batch_size × height × width), e.g., 10 grayscale images of 28×28 pixels  
    → shape = (10, 28, 28)
    
- **4D Tensor:**  
    Batch of RGB images → (batch_size × height × width × channels)  
    → shape = (10, 28, 28, 3)
    

---

## ⚙️ **Why Are Tensors Important in ML?**

1. **Representation of data:**  
    All input data (images, text, audio, etc.) are represented as tensors.
    
2. **Efficient computation:**  
    Tensors allow parallel computation on GPUs and TPUs.
    
3. **Mathematical foundation:**  
    Operations like matrix multiplication, dot products, and transformations are tensor operations.
    
4. **Deep learning models:**  
    Neural networks process and transform tensors layer by layer.
    

---

## 🧮 **Tensor Operations**

Tensors support a wide range of operations (like in NumPy):

- Addition, subtraction: `A + B`
    
- Dot product: `A @ B`
    
- Transpose: `A.T`
    
- Reshape: `A.reshape(new_shape)`
    
- Broadcasting: automatic alignment of dimensions

## 🧠 **Analogy**

Think of a **tensor** like a **container for numbers** that can hold:

- a single number → scalar
    
- a line of numbers → vector
    
- a table of numbers → matrix
    
- or higher-dimensional data → tensor
    

## 💡 Summary

|Concept|Description|
|---|---|
|**Tensor**|Multi-dimensional array used to represent data|
|**Rank**|Number of dimensions (e.g., 0D scalar, 1D vector, 2D matrix)|
|**Shape**|Size along each dimension|
|**Frameworks**|TensorFlow, PyTorch, NumPy|
|**Use**|Represent input data, weights, and outputs in ML models|
