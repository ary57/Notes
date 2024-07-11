<span style="font-family:helvetica-seriff; font-size:1em;">


# Scalars, Vectors, Matrices and Tensors

## Scalar
- A single number.
- Written in Italics
- When introducing - specify what kind of number they are. 
    - Let $s ∈ ℝ$ be the slope of the line. 
    - Let $n ∈ ℕ$ be the number of units.

## Vector
- An array of numbers. 
- Each number in a vector can be identified by it's index. 
- Written bold and lowercase.
    - Each element in the vector is written in lowercase italics with a subscript.
- When introducing - specify what kind of numbers are stored in the vector and it's length. 
    - If each element is in the set of all real numbers ($ℝ$) and the vector has $n$ elements the vector is denoted as $ℝ^{n}$. 

$$x = \begin{bmatrix} x_{1} \\ x_{2} \\ \vdots\ \\ x_{n} \end{bmatrix}$$

- Vectors can be indexed. And to index a set of elements, define a set of indeces and write the set as a subscript. 
    - Example: To access $x_{1}$,$x_{3}$ and $x_{6}$ in a vector $x$, deinfe the set $s = \left\{1,3,6\right\}$ and write $x_{s}$.
- To get the complement use the $-$ sign. `
    - $x_{-s}$ is the set of all elements of $x$ except elements in indeces $s$ .

## Matrix
- 2d array of numbers. 
- Written as uppercase letters with bold typeface.
$$ A = \begin{bmatrix} A_{1,1} & A_{1,2}\\ A_{2,1} & A_{2,2} \end{bmatrix} $$
- Each element is identified by two indeces. 
- Has a height $m$ and width $n$.
- A matrix $A$ with all real values that has height $m$ and width $n$ is represented as: $A \in ℝ^{m*n} $
- Matrix are indexed, just like vectors. 
    - $A_{1,1}$ is the top-left element. 
    - $A_{m,n}$ is the bottom-right element.
    - $:$ can be used to index the whole row or column.
        - $A_{i,:}$ denotes the ith row. 
        - $A_{:,i}$ denotes the ith column. 


## Tensors
- An array of numbers arranged on a regular grid with a variable number of axes.
- 3d (or more) array of numbers. 


# Matrix Operations

## Transpose
- The mirror image of a matrix across a diagonal line. 
- Denoted with a superscript $T$.
    - Example: Transpose of a matrix $A$ is $A^{T}$
$$ (A^{T})_{i,j} = A_{j,i} $$
$$ A = \begin{bmatrix} 
            A_{1,1} & A_{1,2} \\  
            A_{2,1} & A_{2,2} \\  
            A_{3,1} & A_{3,2} \\  
       \end{bmatrix} \to A^{T} = 
       \begin{bmatrix}
            A_{1,1} & A_{2,1} & A_{3,1} \\
            A_{1,2} & A_{2,2} & A_{3,2} 
       \end{bmatrix}
$$
$$ b = \begin{bmatrix}
            b_{1} \\
            b_{2} \\
            b_{3} \\
            b_{4}
       \end{bmatrix} \to b^{T} = 
       \begin{bmatrix}
            b_{1} & b_{2} & b_{3} & b_{4}
       \end{bmatrix}
$$

<div style="page-break-after: always;" ></div>


# Multiplying Matrices and Vectors
## Matrix Product / Standard Product
- The matrix product of matrices $A$ and $B$ is a third matrix $C$.
    - $A$ must have the same number of columns as $B$ has rows.
    - If $A$ is of shape $m \times n$ and $B$ is of shape $n \times p$, then $C$ is of shape $m \times p$.
- Written as $C=AB$.
- The operation is defined as:
$$C_{i,j}=\sum_{k}^{ }A_{i,k}B_{k,j}$$

- The dot product between two vectors $x$ and $y$ with the same dimension is the same as the matrix product $x^{T}y$.

### Matrix product properteis 
Matrix product
- Is distributive
$$A(B+C)=AB+AC$$
- Is associative
$$A(BC)=(AB)C$$
- Is **NOT** commutative
$$A(B+C) \text{ not always } AB+AC$$

## Element-wise Product / Hadamard Product
- A matrix containing the product of individual elements (like matrix addition).
    - Denoted as $A \odot B$.

<div style="page-break-after: always;" ></div>

## System of linear equation
$$Ax=b$$
- Where:
    - $A \in \R^{m \times n}$ is a known matrix.
    - $b \in \R^{m}$ is a known vector.
    - $x \in \R^{n}$ is a vector of unknown variables we're trying to solve for.
- So the equation can be rewritten as:
    $$A_{1,:}x = b_{1}$$

    $$A_{2,:}x = b_{2}$$

    $$\dots$$

    $$A_{m,:}x = b_{m}$$
- Or even explicitly as:
    $$A_{1,1}x_{1} + A_{1,2}x_{2} + \dots + A_{1,n}x_{n} = b_{1}$$
    
    $$A_{2,1}x_{1} + A_{2,2}x_{2} + \dots + A_{2,n}x_{n} = b_{2}$$

    $$\dots $$

    $$A_{m,1}x_{1} + A_{m,2}x_{2} + \dots + A_{m,n}x_{n} = b_{m}$$


</span>
