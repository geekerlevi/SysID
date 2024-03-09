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

[Put discrete-time data in a timetable]

TT = timetable(Torque, Wave_m1p2, Velo,'SampleRate',50);

data=iddata(TT,'OutputName',{'Velo'},'InputName',{'Torque','Wave_m1p2'});
