# Simulation of active vibration damping

Parameters to be considered for writing up the transfer function
<br>
<br>
<table>
  <thead>
    <tr>
      <th>Voltage (V)</th>
      <th>Torque (Nm)</th>
      <th>Rotation speed (1/min)</th>
      <th>Current (A)</th>
      <th>Mechanical power (W)</th>
      <th>Electrical power (W)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>4.5</td>
      <td>0.173</td>
      <td>24</td>
      <td>0.69</td>
      <td>0.43</td>
      <td>3.10</td>
    </tr>
    <tr>
      <td>6</td>
      <td>0.173</td>
      <td>51</td>
      <td>0.69</td>
      <td>0.92</td>
      <td>4.14</td>
    </tr>
    <tr>
      <td>7.5</td>
      <td>0.173</td>
      <td>78</td>
      <td>0.69</td>
      <td>1.41</td>
      <td>5.17</td>
    </tr>
    <tr>
      <td>9</td>
      <td>0.173</td>
      <td>105</td>
      <td>0.69</td>
      <td>1.90</td>
      <td>6.21</td>
    </tr>
    <tr>
      <td>10.5</td>
      <td>0.173</td>
      <td>132</td>
      <td>0.69</td>
      <td>2.39</td>
      <td>7.24</td>
    </tr>
    <tr>
      <td>12</td>
      <td>0.173</td>
      <td>153</td>
      <td>0.69</td>
      <td>2.77</td>
      <td>8.28</td>
    </tr>
  </tbody>
</table>

Technical data on EV3 motor large:

Max. Angular speed: 175 revolutions per minute, see [2].
No-load current: 60 mA, see [2].
Starting torque: 0.43 Nm, see [2, 3]
Drive torque: 0.173 Nm, see [2, 3]

Resistance Ra = 4.196 Ohm, see [5]
Inductance La = 0.00494 H = 4.94 mH, see [5]
(determined by LCR measuring device)

Msys... Mass of the system (weighed) = 0.81 kg
Mr... Mass of the wheels (weighed) = 0.095 kg
J... Mass inertia = 0.0015 kgm2, see [5].
r... Radius of the wheel (measured) = 0.028 m
c*Φ... EMF constant = 0.468 V s/rad, see [1].


Transfer function of the motor, see [8]:
 

Parameter inserted in formula:
F(s)mot = (0.0015/0.468)s / ((0.0015*0.00494)/(0.468²))s² + ((0.0015*4.196)/(0.468²))s + 1
       = 3.21*10-3s / (3.83*10-5s² + 0.029s + 1)

Transfer function of the system, see [9]:
 
Mass of my system: 0.810 kg 
f = 1/T ; T=0,5 s (read from scope figure), see [10].
  = 2 Hz
 

w0 = 2*PI*f = 2*PI*2= 12,57 1/s => w0² = 157,91
Damping constant D = 0.3 (assumption)
Gain factor K = 1
F(s)sys = 157.91 / (s² + 7.54s + 157.91)
