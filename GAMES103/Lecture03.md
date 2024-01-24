# Rigid Body Dynamics
## Rigid Body Simulation
The goal of simulation is to update the state variable **S** over time<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03.png)<br>
If a rigid body cannot deform,its motion consists of two parts:translation and rotation.<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03a.png)<br>
v=上一个时刻的速度(dx/dt)加上加速度的积分=力的积分除以M<br>
(semi-implicit)integration outcome<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03e.png)<br>
leapfrog method,把速度和位置看成错开的<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03f.png)<br>
## Integration Methods Explained
显式积分使用v(t0)<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03b.png)<br>
隐式积分使用v(t1)<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03c.png)<br>
Mid-point积分使用v(t0.5),剩下3阶误差<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03d.png)<br>
## Tpyes of Forces
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03g.png)<br>
## Rigid Body Simulation(Translation Only)
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03h.png)<br>
v[t]Unity里面没有自己设，x[t]有自带的，△t自己改变,不用和帧率对上<br>
## Rotation Represented by Matrix
旋转矩阵优缺点<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03i.png)<br>
## Rotation Represented by Euler Angle
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03j.png)<br>
Gimbal Lock<br>
在旋转轴重合时会丧失一个自由度<br>
## Rotation Represented by Quaternion
使用一个实数三个虚数描述一个3D的点，既能乘也能除,使用向量则无法除<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03k.png)<br>
Quaternion Arithematic<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03l.png)<br>
s:一个实数 **v**:一个向量代表虚数<br>
Unity中xyz对应**V**,w对应s,自带乘法<br>
Rotation Represented by Quaternion<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03m.png)<br>
In Unity<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03n.png)<br>
Roatatinal Motion<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03o.png)<br>
要知道**q**对时间的导数**w**角速度(旋转速度)<br>
Torque(f) and Inertia(M)<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03p.png)<br>
ri/Rri:旋转前/后点的位置 fi:力<br>
Inertia<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03q.png)<br>
对旋转来说M是一个矩阵<br>
mi:每一个点的质量 Iref:ref状态下3x3的矩阵<br>
**更新状态方程**<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03r.png)<br>
最后要normalize**q**.**W**要定义<br>
## overall Rigid Body Simulation
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03s.png)<br>
左边是线性运动，右边是曲线运动<br>
In practice,we update the same state variable s={v,x,w,q}<br>
renew them every time<br>
## implementation Issues
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureA/Lecture03t.png)<br>




