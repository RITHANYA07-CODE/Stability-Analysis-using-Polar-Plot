# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:

<img width="1080" height="1147" alt="image" src="https://github.com/user-attachments/assets/f2ca3764-b575-4b2d-8793-7f86b32331ec" />

<img width="778" height="1280" alt="image" src="https://github.com/user-attachments/assets/fe1e4e0f-2bf4-4067-b2ad-47762a6227ab" />

<img width="944" height="1280" alt="image" src="https://github.com/user-attachments/assets/e810bab6-d27a-4a98-b10d-32688a0a7a0a" />

## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[10]
den=[0.1 0.7 1 0]
sys=tf(num,den)
[mag,phase,W]=bode(sys)
mag=squeeze(mag)
phase=squeeze(phase)
phase1=deg2rad(phase)
polarplot(phase1,mag,'linewidth',1.5)
grid on
[Gm Pm Wpc Wgc]=margin(sys)
if(Wpc>Wgc)
    disp('stable')
elseif(Wpc == Wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```
## Output:

<img width="1053" height="985" alt="image" src="https://github.com/user-attachments/assets/24191fc3-ac73-4201-96dd-624d62738f40" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB.<br>
Gain margin = 0.7<br>
Phase Margin = -8.8865<br>
Gain crossover frequency = 3.7565<br>
Phase crossover frequency = 3.1623<br>
The system is unstable.<br>
