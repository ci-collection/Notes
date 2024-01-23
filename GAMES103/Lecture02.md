# Vector,Matrix and Tensor Calculus
## Vertor
### Definition
Definition:A geometric entity endowed  with magnitude and direction.<br>
通常使用黑体代表向量，斜体为标量，不使用箭头<br>
**q**从原点出发的一条向量，也可以看成一个点<br>
<br>
Right-Hand System 右手坐标系<br>
四指从x轴到y轴，大拇指方向为z轴<br>
常用于研究中和OPenGl<br>
<br>
Left-Hand System<br>
Unity and DirectX<br>
<br>
Largely due to:convention of the screen space.<br>
Using Left-Hand System z direction is into the screen,z value is positive.<br>
<br>
Vector may not a geometric vector,but a stacked vector.e.g.11个点的集合，没有几何意义，表示物体状态.<br>
<br>
Addition is commutative.p+q=q+p<br>
### Linear Representation
Position:p(t)=p+tv<br>
p:point formal positon; v:moving direction/force; t:time.<br>
t>0 v+direction;t<0 v=direction<br>
<br>
A line:p(t)=p+t(q-p).<br>
p.q:two points; q-p stands for direction.<br>
t>1 q-p direction; 0<t<1 on qpline; t<0 -(q-p) direction<br>
A segment:0<t<1<br>
A ray:0<t<br>
A line:t∈R<br>
<br>
Or p(t)=(1=t)p+tq<br>
(1-t)p的权重;t是q的权重<br>
就是对p和q进行线性混合，叫做插值.t is an interpolant.<br>
### Vector Norm
Euclidean norm(2-norm) Px,Py,Pz平方和开根号.<br>
p-norm Px,Py,Pz p次方和开p根号.<br>
1-norm(Manhattan Distance) Px,Py,Pz 绝对值的和.<br>
infinity norm Px,Py,Pz p无限，绝对值中的最大值.<br>
<br>
Distance between q and p:||q-p||<br>
A unit vector:||p||=1.<br>
Normalization:p=p/||p||<br>
### Vector Arithematic:Dot Product
A dot product,also called inner product,is:<br>
<p,q>/p•q=PxQx+PyQy+PzQz=p⊤q=||p||||q||cos⊖<br>
p•q=q•p<br>
p•p=||p||² 在积分时代替norm.<br>
p•q=0,then p and q are orthogonal.<br>
### Particle-Line Projection
o:origin; q:particle point; v:direction projected; s:projection distance<br>
s=||q-o||cos⊖<br>
s=(q-o)⊤v/||v||=(q-o)⊤(normalized v)<br>
**s**:projection vector <br> 
**s**=o+s(normalized v)<br>
### Plane Representation
判断p点是不是在平面上<br>
**p**:p point; **c**:one point on plane;**n**:(normalized) normal vector<br>
s=(**p**-**c**)⊤**n**<br>
s=0 On the plane<br>
s:signed distance to the plane.有符号的距离<br>
### Particle-Sphere Collision
粒子p沿着v碰撞到圆心为c的圆，碰撞点是**p**(t).<bt>
||**p**(t)-**c**||² =r² <br>
(**p**-**c**+t**v**)•(**p**-**c**+t**v**)=r²<br>
(**v**•**v**)t²+2(**p**-**c**)•**v**t+(**p**-**c**)•(**p**-**c**)-r²=0<br>
关于t的一元二次方程<br>
*No root:不相交<br>
*One root:相切<br>
*Two root:穿过<br>
### Vector Arithematic:Cross Product
The result of a product is a vector:**r**=**p**x**q**<br>
**r**•**p**=0 **r**•**q**=0 ||**r**||=||**p**||||**q**||sin⊖<br>
**p**x**q**=-**q**x**p**<br>
if **p**x**q**=0,then **p**and**q** are parallel.<br>
### Triangle Normal and Area
**x0**,**x1**,**x2** three points ⊖**x0**Angle<br>
Edge vectors:**x10**=**x1**-**x0** **x20**=**x2**-**x0**<br>
Normal:**n**=(**x10**x**x20**)/||**x10**x**x20**||<br>
Area:A=||**x10**||||**x20**||sin⊖/2=||**x10**x**x20**||/2<br>
The normal depends on the triangle index order(顶点顺序),also known as topological order.<br>
### Triangle Inside/Outside Test
点p相对于**x0**,**x1**来说，是不是在**x2**那边,四个点全在同一平面上<br>
如果在同侧，叉乘结果与**n**相同方向<br>
if **p**is inside of **x0****x1**,then:(**x0**-**p**)x(**x1**-**p**)•**n**>0<br>
三条边全部>0,Inside of triangle<br>
### Barycentric Coordinates
A2:signed area<br>
Inside:(**x0**-**p**)x(**x1**-**p**)•**n**/2=||(**x0**-**p**)x(**x1**-**p**)||/2=A2<br>
Outside=Negative=A2<br>
A=A0+A1+A2<br>
Barycentric weights of **p**:b0=A0/A b1=A1/A b2=A2/A<br>
b0+b1+b2=1<br>
Barycentric Interpolation:**p**=b0**x0**+b1**x1**+b2**x2**
算p点位置颜色<br>
Barycentric weight allows the interior points of a triangle to be interpolated.<br>
Gouraud shading:In a traditional graghic pipeline,pixel colors are calculated at triangle vertices first,and then interpolated within.<br>
### Tetrahedral Volume
Edge vectors:**X10**=**x1**-**x0** **x20**=**x2**-**x0** **x30**=**x3**=**x0**<br>
Base triangle area:A=||**x10**x**x20**||/2<br>
Height:h=**x30**•**n**(在n上的投影)=**x30**•**x10**x**x20**/||**X10**x**x20**||<br>
Volume:V=hA/3=**x30**•**x10**x**x20**/6<br>
### Barycentric Weights
**p** splits the tetrahedron into four sub-tetrahedra:V1,V2,V3,V0<br>
**p** is inside if and only if:V0,V1,V2,V3>0<br>
b0=V0/V b1 b2 b3<br>
**p**=b0**x0**+b1**x1**+b2**x2**+b3**x3**<br>
### Particle-triangle Intersection
三角形不动，粒子撞击<br>
Find t when the particle hits the plane:(**p**-**X0**+t**v**)•**x10**x**x20**=0<br>
then check if **p(t)** is inside or not
## Matrices
Definition:A real matrix is a set of real elements arranged in rows and columns.<br>
Transpose:A⊤<br>
Symmetric:沿着对角的轴对称 A=A⊤<br>
Diagonal:对角上有值，其他地方全是0.<br>
identity:对角上全是1，其他全是0.<br>
### Matrix:Multiplication
Omitted<br>
AB not= BA  (AB)⊤=B⊤A⊤ AA⊤即为对称矩阵.(A⊤A)⊤=AA⊤<br>
A+A⊤也是symmetric<br>
AA⁻¹=I inverse. (AB)⁻¹=B⁻¹A⁻¹<br>
Not every matrix is invertible.e.g.A=[0]<br>
### Matrix:Orthogonality
An orthogonal matrix is a matrix made of orthogonal unit vectors.<br>
里面全是相互正交的单位矩阵.<br>
A⊤A=I then A⊤=A⁻¹<br>
### Matrix Transformation
A rotation can be represented by an orthogonal matrix.<br>
**uvw**是旋转后的物体坐标系.<br>
A**x**=**u** A**y**=**v** A**x**=**w**<br>
AI=[**u v w**]=A then A is orthogonal matrix.<br>
<br>
A scaling can be represented by a diagonal matrix.<br>
D=[dx dy dz] consisting of scaling factors.<br>
### Singular Value Decomposition 奇异值分解
A matrix can be decomposed into: **A**=**UDV**⊤.<br>
such that **D** is diagonal,and **U** and **V** are orthogonal. **D** is Singular Value.<br>
Graphic meaning:<br>
Any linear deformation can be decomposed into three steps:rotation,scaling and rotation.<br>
### Eigenvalue Decomposition 特征值分解
A symmetric matrix can be decomposed into:A=UDU⊤<br>
such that **D** is diagonal,and**U** is orthogonal. **D**is Eigenvalue.<br>
### Symmetric Positive Definition
**A** is s.p.d.if only if:**v⊤Av**>0,for any **V**≠0.<br>
**A** is symmetric semi-definite if only if:**v⊤Av**≥0,for any**v**≠0.<br>
meaning:d>0 **v⊤dv**>0<br>
d0,d1..>0 **v⊤Dv**=**v⊤[di diagonal matrix]v**>0<br>
**v⊤(UDU⊤)v**=**(U⊤v)(D)(U⊤v)**>0 **U**orthogonal.<br>
A is s.p.d.if only if all of its eigenvalues are positive.d0,d1..>0<br>
A diagonally dominant matrix is s.p.d.<br>
diagonally dominant matrix:对角上的值大于非对角绝对值的和<br>
A s.p.d matrix is invertible.A⁻¹can't be [0]<br>
<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/picture/Lecture02.png)
<br>
### Linear Solver
Many numerical problems are ended up with solving a linear system:<br>
**A**x=**b**<br>
**A**:square matrix **b**:boundary vector x:unknown to be founded<br>
x=**A⁻¹b** but it's too expensive to compute **A⁻¹**<br>
<br>
Direct Linear Solver<br>
A direct solver is typically based LU factorization,or its variant:Cholesky...<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/picture/Lecture02a.png)<br>










