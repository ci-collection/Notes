# Vector,Matrix and Tensor Calculus
## Vertor
### Definition
Definition:A geometric entity endowed  with magnitude and direction.<br>
通常使用黑体代表向量，斜体为标量，不使用箭头<br>
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
A line:t=R<br>
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
###


