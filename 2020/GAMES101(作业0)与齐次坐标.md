# GAMES101(作业0)与齐次坐标



## 作业描述

给定一个点P=(2,1), 将该点绕原点先逆时针旋转45◦，再平移(1,2), 计算出变换后点的坐标（要求用齐次坐标进行计算）。



## 代码

```c++
#include <cmath>
#include <eigen3/Eigen/Core>
#include <eigen3/Eigen/Dense>
#include <iostream>

int main()
{
    std::cout << "point Rotation and Translation \n";
    Eigen::Vector3f p(2.0f,1.0f,0.0f);
    std::cout << p << std::endl;

    Eigen::Matrix3f r,t;
    // point Roatation
    r << 0.5, -0.5, 0.0, 0.5, 0.5, 0.0, 0.0, 0.0, 1.0;
    //point Translation
    t << 1.0, 0.0, 1.0, 0.0, 1.0, 2.0, 0.0, 0.0, 1.0;

    p =  t * r * p;
    std::cout << "point p after rotation and translation is \n" << p << std::endl;
    return 0;
}
```



## 显示结果

```
point Rotation and Translation 
2
1
0
point p after rotation and translation is 
0.5
1.5
  0
```

