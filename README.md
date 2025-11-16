# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:

![WhatsApp Image 2025-11-16 at 15 20 22_1c37cebe](https://github.com/user-attachments/assets/9a7e1467-4e8a-40cb-9156-e833d61038ac)

![WhatsApp Image 2025-11-16 at 15 20 22_cc90499d](https://github.com/user-attachments/assets/5453121f-146f-4155-8160-0a7e256675b7)

![WhatsApp Image 2025-11-16 at 15 20 21_d159a2a8](https://github.com/user-attachments/assets/41686ada-4588-4862-8e73-e2097e3388f3)

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

<img width="1055" height="975" alt="image" src="https://github.com/user-attachments/assets/bd1578ec-3fae-4474-8462-abf0c6d23f8e" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 3.57 dB <br>
Phase Margin = 27.9 degrees <br>
Gain crossover frequency = 1.76 rad/sec <br>
Phase crossover frequency = 4.47 rad/sec <br>
The system is stable.
