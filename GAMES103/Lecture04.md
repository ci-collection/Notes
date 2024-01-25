# Rigid Body Contacts
## Particle Collision Detection and Response
### Signed Distance Function
A signed distance function ∅(x) defines the distance from x to a surface with a sign.<br>
The sign indicates on which side x is located.>0 outside ; <0 inside ; =0 on the surface<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04.png)<br>
### Intersection of Signed Distance Function
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04a.png)<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04b.png)<br>
在外侧就不用算minmax，因为没有碰撞<br>
### Quadratic Penalty Method
A penalty method applies a penalty force in the next update.When the penalty potential is quadratic,the force is linear.<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04c.png)<br>
方向是∇∅(x)使他增大最快；大小是-∅(x)为正值.k类似弹簧系数<br>
缺点是一定会穿模<br>
### Quadratic Penalty Method with a Buffer
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04d.png)<br>
给一个缓冲空间，但是物体v太大，F可能推不动，也可能飞太远 overshooting<br>
### Log-Barrier Penalty Method
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04e.png)<br>
利用距离减小系数<br>
绝不能发生穿透，使用小步长增加了消耗<br>
### Summary of Penalty Methods
The use of step size adjustment is a must.<br>
 To avoid overshooting<br>
 To avoid penetration in log-barrier methods.<br>
Log-barrier method can be limited within a buffer as well.
Frictional contacts are difficult to handle.<br>
### Impulse Method
An impulse method assumes that collision changes the position and the velocity all of suddenn.<br>
位置![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04f.png)<br>
速度![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04g.png)<br>
ųn在0~1之间防止overshooting a是摩擦导致水平方向的衰减<br>
a满足库伦定律 ųt是某一个摩擦系数 max:摩擦力不会让水平速度反转<br>
max(dynamic friction,static friction)<br>
## Rigid Body Collision Detection and Response
### Rigid Body Collision Detection
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04h.png)<br>
表面点的位置Xi 质心点X 检测∅(x)>0<br>
### Rigid Body Collision Response by Impulse
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04i.png)<br>
**v**质点的速度
Problem:we cannot directly modify Xi or Vi,since they are not state variables<br>
Impulse 简化只修改Vi 也就是说只用改**v**和**w**<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04j.png)
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04k.png)
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04l.png)<br>
Impulse反求j:j change **vnew wnew**change **vinew**change and compare with **vi** <br>
△**vi**=Kj receive j<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04m.png)<br>
### Implementation Details
If there are many vertices in collision,we use their averge position.<br>
We can decrease the restitution ųn to reduce oscillation(由于受重力不断弹跳)<br>
We don't renew position here.<br>
## Shape Match
### Basic Idea
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04n.png)<br>
粒子模拟再让点重新聚合回一个缸体<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04o.png)<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04p.png)<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04q.png)<br>
刚体不想要本地形变直接删去S<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04r.png)<br>
![](https://github.com/ci-collection/Notes/blob/main/GAMES103/pictureB/Lecture04s.png)<br>





