Hello Jeremy and Joan,
first of all, thank you for the great overview paper and library! It really allowed me to get a quick overview of the most important ideas behind Lie groups even though I had never heard of them before!

As someone who is quite new to robotics and state/pose estimation, I'm wondering what the motivation for using an error-state KF instead of a regular EKF is for the localization example in section V-A?
I can see that tracking the pose (non-linear globally, because its part of a Lie group) using a separate "object" and then just operating on tangent vectors like in a regular KF is quite elegant, because vector addition and covariance definition now actually make sense.
Is this the natural solution to building a KF state estimator using Lie group theory as presented in the paper?
Is the ESKF solution a natural choice in IMU driven systems, where IMU measurements are available and need to be integrated into the state at high rate, so that interpreting IMU data as a control input circumvents the expensive EKF update step?

I'm wondering if it would be possible to define something more akin to a "normal" EKF that also allows me to track the velocity in the tangent space correctly (x velocity, y velocity and yaw rate)?
```math
X \in \operatorname{SE}\left(2\right)
v \in \Real^3
\mu = \left( \operatorname{Log}\left(X\right)^T v^T \right)^T
```
