Title: Offline system identification of wave energy converter and analysis

Introduction: 
This code delves into black-box discrete-time system identification for offline wave energy converters (WECs), aiming to compare multiple models based on the principles of system identification. The investigation encompasses various models, including the transfer function model, state space model, autoregressive exogenous input (ARX) model, and Hammerstein Wiener model, with different orders of the system under scrutiny. Each model's realization theory is elaborated, and supported by mathematical expressions and, in some instances, block diagrams. The algorithms utilize functions such as tfest, n4sid, arx, and nlhw within the System Identification Toolbox (Release 2023b, designed for MATLAB), leveraging time domain data collected from FloWave tank facilities in Edinburgh. The experimental data is derived from irregular waves characterized by wave periods ranging from 6.3 seconds to 14.7 seconds and wave heights spanning from 1.5 meters to 2.5 meters, at a 1/20th scale. Both small (i.e., with wave heights of 1.5 meters) and large (i.e., with wave height of 2.5 meters) wave conditions are meticulously examined and compared using the identified models proposed in this study. Additionally, the report provides a comprehensive discussion of the findings and outlines potential avenues for future research endeavors.



A comparison between sysID models:

1: Transfer Function

2: State-space model

3: ARX :   Opt.Focus = 'simulation';

4: Hammerstein Wiener Model


The variable in the experiment is the order of the system:
Order: 

-> 4

-> 6

-> 12

-> 18

-> 24

-> 30


Implementation: 

[1]Initialize data

[Put discrete-time data in a timetable]

TT = timetable(Torque, Wave_m1p2, Velo,'SampleRate',50);

data=iddata(TT,'OutputName',{'Velo'},'InputName',{'Torque','Wave_m1p2'});

de=data(1:22000);

dv=data(22000:32950);

[2] Run model

Use the corresponding code:

Wave_condition_a_b
where (a=1/ 2/ 3/ 4/ 5/ 6/ 7/ 8/ 9/ 10/ 11/ 12, b= tf/ ss/ arx/ nlhw)
