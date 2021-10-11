# Python Umeyama's algorithm
A python implementation of Umeyama's algorithm presented in [Least-Squares Estimation of Transformation Parameters Between Two Point Patterns](https://web.stanford.edu/class/cs273/refs/umeyama.pdf) (Shinji Umeyama, 1991).

## Description
Let *X* be a set of *n* *m*-dimensional points in a given frame. Let *Y* be a set of the same *m*-dimensional points in another frame. We have *X = {x1, x2, ..., xn}*, *Y={y1, y2, ... yn}* where *xi* and *yi* are *m*-dimenstional points. We want to find the transformation from one frame to another such as it minimizes the mean square error between the two sets of points.  
More specifically, we want to find *[c, R, t] ∈ Sim(3)* given the minimum value of *MSE(Y, c * R · X + t)*.  
Notations in the code are consistent with the paper.

## Usage
Let `X` and `Y` be 3D numpy arrays with shape (m, n) and consistent indexes.  
First, import `umeyama` function from [umeyama.py](umeyama.py).  
Then ```c, R, t = umeyama(X, Y)``` returns `c`, `R` and `t` such as Y ~ ```c * R @ X + t```.

## Example
We provide an example in the IPython notebook [example.ipynb](example.ipynb).
