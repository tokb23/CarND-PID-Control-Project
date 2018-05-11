# Reflection

### Describe the effect each of the P, I, D components had in your implementation.

The P (proportional) component is proportional to the cross track error (CTE). So when the CTE is high, it forces the car to get back on the right trajectory, or often it does so hard so that the car might overshoot or start oscillating.

The D (differential) component takes the change rate of the CTE into account. It can smooth the steering of the car which means that it can mitigate overshooting or oscillating (the effect caused by P).

The I (integral) component contains the sum of the CTE over the past. It can prevent the car from being one side and far from the middle of the road, mainly caused by systematic bias.

### Describe how the final hyperparameters were chosen.

Since the car doesn't have a systematic bias, I just ignored the I component.
I did manual tuning for P and D components. When I only set P or set it to a high number, the car started oscillating so hard. It could be mitigated by setting D to high value compared to P or decrease P.
In the end, I set P to a small value and D to a bit high value.
