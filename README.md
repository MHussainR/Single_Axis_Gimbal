# Inertial Platform Stabilizer

## Introduction
This project introduces an innovative approach in the field of motion stabilization. We develop a single-axis gimbal system integrated with an Inertial Measurement Unit (IMU) sensor and a carefully calibrated Proportional-Integral-Derivative (PID) controller. The actuator and stable platform exhibit a symbiotic relationship, ensuring stability despite external motions or disturbances. The IMU sensor is crucial for real-time orientation monitoring, capturing minute angular variations with precision. The PID controller organizes precise adjustments to counteract external disturbances, ensuring the platform’s resilience.

## Methods & Materials

### Mathematical Modelling of Plant, Actuators, and Sensors

#### Controller Model
The PID controller is a fundamental component employed inside control systems. The primary objective is to efficiently govern and maintain optimal setpoints by employing three control actions: Proportional (P), Integral (I), and Derivative (D). The transfer function for the controller is given by:

\[ C(s) = K_P + sK_D + \frac{K_I}{s} \]

Where:
- \( K_P \): Proportional Gain
- \( K_I \): Integral Gain
- \( K_D \): Derivative Gain

#### Actuator Model
The actuator transfer function is given by:

\[ T(s) = \frac{K_t(N2/N1)}{s\{(Js+D)(sLa+Ra) + K_t^2\}} \]

Where:
- \( K_t \): Motor Torque Constant
- \( J \): Moment of Inertia
- \( s \): Laplace variable
- \( D \): Damping or friction in the system
- \( La \): Motor inductance
- \( Ra \): Motor resistance
- \( N2/N1 \): Gear ratio

#### Model of Plant
The moment of inertia of the plant is given by:

\[ J = \frac{1}{12} \cdot m \cdot (a^2 + b^2) \]

Where:
- \( J \): Moment of Inertia
- \( m \): Mass of the sheet
- \( a \): Length of one side of the sheet
- \( b \): Length of the other side of the sheet

#### Model of Gyroscopic Sensor
The gyroscopic sensor model is represented as a second-order transfer function:

\[ G_g(s) = \frac{\omega_n^2}{s^2 + 2\zeta \omega_n s + \omega_n^2} \]

Where:
- \( \zeta \): Damping ratio of the gyroscope
- \( \omega_n \): Natural frequency of the gyroscope

### Model Validation
Model validation is performed using Simulink block diagrams and output graphs for motor, plant, and gyroscope models.

### Gimbal Dynamics: Precision Analysis & Model Validation
Simulink block diagrams are used to represent the entire project, consisting of an input signal, a PID controller, the plant, MPU (gyroscope), and an integrator at the output.

#### Highly Fine Tuned Model
Using a PID Controller to tune the system achieves an output response with no error between the output and the input signals. The PID values are tuned to achieve the desired response.

#### Realistically Tuned Model
The model is tuned to achieve a response more realistic according to IEEE literature, improving the stability of the mass on the platform.

### Physical Design
A wooden frame was created for the single axis. An ESP 32 was used as a controller, an MPU 6050 as the IMU Sensor, and a JGA 25371 GearMotor as the actuator.

## Conclusion
This project developed a reliable and automated single-axis gimbal system enhancing precision in motion stabilization. Despite certain limitations, the primary aim of developing a stable platform was achieved.

## References
Refer to the detailed report for a comprehensive list of references.