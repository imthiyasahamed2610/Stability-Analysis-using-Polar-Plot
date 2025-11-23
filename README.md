mom# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:

![cs](https://github.com/user-attachments/assets/11ec7b2c-8943-4c68-b375-526c3c08a23f)
![cs2](https://github.com/user-attachments/assets/741c0643-e59a-4b5e-af9b-d779caa67fc2)
![WhatsApp Image 2025-11-16 at 15 20 21_7861d614](https://github.com/user-attachments/assets/ade524d0-9a0e-4e83-b6cb-b3c79047007e)

## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[1]
den=[conv(1,0),conv(1,0.5),conv(1,0.2)]
sys=tf(num,den)
w=logspace(-1,2,1000)
[mag phase]=bode(sys,w)
mag=squeeze(mag)
phase=squeeze(phase)
theta=deg2rad(phase)
polarplot(theta,mag,'LineWidth',1.5)
[gm pm wpc wgc]=margin(sys)
if (wpc>wgc)
    disp('stable')
elseif (wpc==wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```
## Output:

<img width="1053" height="985" alt="17638965676474999459163326062293" src="https://github.com/user-attachments/assets/a0a20a2c-8548-4f86-be72-aec83a46628c" />


## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 0.7000 dB

Phase Margin = 55.6412 deg

Gain crossover frequency = 0.8979 rad/sec

Phase crossover frequency = 3.1623 rad/sec

The system is stable.
