# Rigid Body Dynamics
## Rigid Body Simulation
The goal of simulation is to update the state variable **S** over time<br>
0<br>
If a rigid body cannot deform,its motion consists of two parts:translation and rotation.<br>
a<br>
v=上一个时刻的速度(dx/dt)加上加速度的积分=力的积分除以M<br>
(semi-implicit)integration<br>
e<br>
leapfrog method,把速度和位置看成错开的<br>
f<br>
## Integration Methods Explained
显式积分使用v(t0)<br>
b<br>
隐式积分使用v(t1)<br>
c<br>
Mid-point积分使用v(t0.5),剩下3阶误差<br>
d<br>
## Tpyes of Forces
g<br>
## Rigid Body Simulation(Translation Only)
h<br>
v[t]Unity里面没有自己设，x[t]有自带的，△t自己改变,不用和帧率对上<br>
## Rotation Represented by Matrix
旋转矩阵优缺点<br>
i<br>
## Rotation Represented by Euler Angle
j<br>
Gimbal Lock<br>
在旋转轴重合时会丧失一个自由度<br>
## Rotation Represented by Quaternion
使用一个实数三个虚数描述一个3D的点，既能乘也能除,使用向量则无法除<br>
k<br>
Quaternion Arithematic<br>
L<br>
s:一个实数 **v**:一个向量代表虚数<br>
Unity中xyz对应**V**,w对应s,自带乘法<br>
Rotation Represented by Quaternion<br>
m<br>
In Unity<br>
n<br>



