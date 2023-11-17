# Transmission-Line-Impedance-Calculator-and-Visualization-Tool
Consider a plane wave (having angular frequency of ω rad/sec and phase constant of β rad/m) 
propagating along a transmission line and terminated by a load impedance ZL. The transmission line has a 
characteristic impedance of Zo (=Ro + jXo) and length of l. Plot the input impedance Zi of the transmission 
line for different values of the load impedance ZL (=RL + jXL). Note: the parameter l should be considered 
as input in terms of λ. The parameter values ω, β, l, R0, X0, RL, XL will be provided from user-end. 
We designed an app using MATLAB through which we can calculate input impedance Zi of the 
transmission line for different values of ω, β, l, Zo, ZL and α. And can generate plot for range of load 
impedance between Rin VS ZL and Xin VS ZL. 
For the calculation of input impedance Zi :- 
By providing β, l, Ro, X0, RL, XL and α we can calculate Zi  
λ = 2* π/ β 
ZL = RL + 1j* XL 
Zo = R0 + 1j* X0 
g = α + 1j* β 
Zi = Zo *(( ZL + Zo *tanh(g*l))/( Zo + ZL *tanh(g*l))) 
 
Plotting Rin VS ZL :- 
 
λ = 2* π/ β 
Zo = R0 + 1j* X0 
g = α + 1j* β 
x = [R_start:0.1:R_end] 
y = [X_start,0.1:X_end] 
[xx,yy] = meshgrid(x,y) 
ZL = (xx) + 1j*(yy) 
zzz = Zo.*(( ZL + Zo *tanh(g*l))/( Zo + tanh(g*l).* ZL)) 
zz = real(zzz) 
mesh(xx,yy,zz) 
 
Plotting Xin VS ZL :- 
 
λ = 2* π/ β 
Zo = R0 + 1j* X0 
g = α + 1j* β 
x = [R_start:0.1:R_end] 
y = [X_start,0.1:X_end] 
[xx,yy] = meshgrid(x,y) 
ZL = (xx) + 1j*(yy) 
zzz = Zo.*(( ZL + Zo *tanh(g*l))/( Zo + tanh(g*l).* ZL)) 
zz = imag(zzz) 
mesh(xx,yy,zz) 
 
x = [R_start:0.1:R_end] and y = [X_start,0.1:X_end] :- range of x and y for generating plots. 
meshgrid :- used to create rectangular structures from the given arrays which represent the indexing in the 
matrix. 
mesh(X,Y,Z) :- creates a mesh plot, which is a three-dimensional surface that has solid edge colours and 
no face colours. The function plots the values in matrix Z as heights above a grid in the x-y plane defined 
by X and Y. The edge colours vary according to the heights specified by Z.
