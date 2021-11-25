# ELL706_Assignment2

# Problem 1 [Energy Minimization] (7 points)

Consider a unit mass electric vehicle with position x(t)∈R, moving with velocity v(t) and acceleration a(t). The vehicle needs to be maneuvred from initial position of rest to final position x(T) at time t=T satisfying  x(T)≥xf. Requirements are v˙≤A, 0≤v(t)≤V, v(T)≤vf

Let p(t),pb(t),pd(t) be power delivered by battery, power lost in braking, power lost due to drag respectively and k(t) be kinetic energy of vehicle which is v(t)2/2. Then,
p(t)=k˙(t)+pb(t)+pd(t)
where, pd(t)=cv(t)3 and the power used for braking pb(t) can be controlled. 

Take T=nh and divide interval [0,T] into n subintervals of length h to discretize the vehicle equations of motion,
x˙=v,v˙=a.
In discrete form we get following equations 

xr+1=xr+h(vr+vr+1)/2

vr+1=vr+har

pr=(kr+1−kr)/h+pb,r+pd,r

kr=v2r/2

Total energy consumed is E=h∑nr=0pr.

1. Formulate an optimization problem for minimum energy consumption. Write all variables and constraints on them. Indicate decision variables. Comment on the nature of the problem. 

2. Solve the problem by taking xf=12 m,vf=2 m/s,V=10 m/s,A=2 m/s2,c=2,h=0.1,T=5 s. Experiment by changing the values of xf,vf,V,A and compare the results. Plot x(t),v(t),p(t) v/s time on separate graphs.

3. Make a relaxation in the equality constraint kr=v2r/2, by replacing it with constraint kr≥v2r/2. Make reasonable additional assumptions and see if the problem can be converted into convex optimization problem. Solve the problem for above values and note down your observations. Justify these observations.


Problem 2 [Variational Form of Circuit Equations] (7 points)
Consider a circuit with m branches and n nodes. Let vector e∈Rn denote node voltages, v∈Rm denote branch voltages and i∈Rm denote branch currents.  Also, let the current-voltage characteristics of a two terminal device present in branch k be given by function vk=fk(ik). For example, if the device is resistor of resistance R then vk=ikR, if the device is voltage source of Vk volts with resistance r then vk=Vk+ikrk. According to KCL, the current vector i satisfies, Ai=0 where A∈Rn×m is node-edge incidence matrix. Similarly, KVL gives v=A⊤e. Now consider function
Φ(i)=∑k=1m∫ik0fk(zk)dzk

1. Write the dual of following optimization problem. Note the problem is equality constrained one. Indicate key differences w.r.t. the inequality constrained case in terms of Lagrange multipliers, constraints, etc.

minimize Φ(i)

s.t. Ai=0

2. Make use of KKT conditions. Comment on the equations obtained from the dual formulation. 

3. Solve the following circuits by solving both primal and dual formulation. Comment on the results.

a. Circuit with nodes = {1,2,3,4,5}, branches = {(12,R),(23,R),(34,R),(45,R),(24,R),(35,R),(25,R),(15,V)} where R indicates resistor in the branch, V indicates a voltage source in the branch.  R12=10Ω, R23=100Ω, R34=10Ω, R45=100Ω, R25=10Ω, R35=10Ω, R24=10Ω, V=10V with internal resistance of 2Ω.

b. Circuit with nodes = {1,2,3,4,5}, branches = {(12,R),(23,R),(34,D1, |>|),(45,R),(35,D2, |>|),(25,R),(15,V)}. R12 =1000Ω, R23=1000Ω, R25=1000Ω, R45 = 100Ω D1, D2 are diodes with VT=30mV and Is=0.5mA, V=1V with internal resistance of 1Ω. Take for diode vk=VTlog(1+ik/Is).



(Possible solvers that can be used are CVX for Python https://cvxopt.org/userguide/solvers.html, CVX for Matlab http://cvxr.com/cvx/doc/quickstart.html, 'fmincon' for matlab. Depending on the nature of problem you may search and choose any other solver too if you find it to be suitable. Justify your choice in your response. ).
