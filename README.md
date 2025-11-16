# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
<img width="1053" height="1600" alt="image" src="https://github.com/user-attachments/assets/b11eeb26-146b-4df2-b2e1-2a757f16cde6" />
<img width="1029" height="1454" alt="image" src="https://github.com/user-attachments/assets/e628721b-bd2a-41c3-a5f4-063dfa43e1cc" />

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
<img width="1789" height="825" alt="Screenshot 2025-11-16 104814" src="https://github.com/user-attachments/assets/2036c1eb-5995-4170-97e6-280623eb9e5e" />


## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin =-23.10db <br>
Phase Margin =-50.48 <br>
Gain crossover frequency = 0.9534 rad/s<br>
Phase crossover frequency =0.3162rad/s <br>
The system is  unstable------------
