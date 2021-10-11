# Python Umeyama's algorithm
A python implementation of Umeyama's algorithm presented in [Least-Squares Estimation of Transformation Parameters Between Two Point Patterns](https://web.stanford.edu/class/cs273/refs/umeyama.pdf) (Shinji Umeyama, 1991).

## Description
Let $X$ be a set of $n$ $m$-dimensional points in a given frame. Let $Y$ be a set of the same $m$-dimensional points in another frame. We have $X = \{x_1, x_2, ..., x_n\}, Y=\{y_1, y_2, ... y_n\}$ where $x_i$ and $y_i$ are $m$-dimenstional points. We want to find the transformation from one frame to another such as it minimizes the mean square error between the two sets of points.  
More specifically, we want to find $[c, R, t] \in Sim(3)$ given the minimum value of $\frac{1}{n} \sum_{i=1}^n \left\Vert y_i - (cRx_i + t)\right\Vert^2$.  
Notations in the code are consistent with the paper.

## Usage
Let `X` and `Y` be 3D numpy arrays with shape ($m$, $n$) and consistent indexes.  
```c, R, t = umeyama(X, Y)``` returns `c`, `R` and `t` such as Y ~ ```c * R @ X + t```.

## Example
We provide an example in the IPython notebook [example.ipynb](example.ipynb).
