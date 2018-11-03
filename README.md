# Course Notes
===========================
## 1.How to build a simulator for an estimation method?
**1).Define the elements in the state.**
**2).Path Generation**
This func produce the series of state. e.g. x=[...], x_dot=[...], x_dot_dot = [...], theta=[...] .......   
**3).Get the raw measurement data**
Generate the noisy measurement from the perfect actual state. And define the elements in the state.        
**4).Raw measurement data-----> Estimate data**       
**5).Implement the dynamics of the machine(robot/drone) to predict next state.**   
  
|Known|What we want|
|----|-----|
|Thrust/Angular velocity |Acceleration|       

**6).Controllers use different kinds of data. And simulate the states of the machine.**
The controllers may be a PID controller or sth similar, but the data they use are different. So We can understand the influence of estimation.           
Controller 1:  PID_controller_with_measured_values            
Controller 2:  PID_controller_with_estimated_values         
     

## 2.Get to know estimation methods step by step
**Only use measurement.** Simply just the average ---or--- Recursive average (which is a kind of weighted average).         
**Not only use measurement, but also use the control to predict the state.** Bayes Filters are introduced.          
**Kalman Filter.**  Gaussian + Matrices.       
**Extend Kalman Filter(EKF).** Gaussian + Nonlinear-----Linearize----->Make it linear and use Kalman Filter.     
**Unscented Kalman Filter(UKF).** Gaussian + Nonlinear-->Don't need the linearization step.        
**Particle Filter.** Not Gaussian + Nonlinear         

## 3.In estimation problems, how to understand the word "state"?        
State means several different things: and in the course they are mentioned like this:        
1).ture state / acutal state      
2).measured state / measurement       
3).estimate state / estimation /belif        
4).predicted state / predict / belif_bar        
**In coding, for Kalman Filter how to represent the state?**           
Kalman Filter: state is a Gaussian, just use mean and covariance.    
here state mentioned means: estimated state and predicted state, and in the course pseudo-code they use the symbol bel and bel_bar respectively.        
**For the pseudocode, how to reprsent state**               
**Simplified procedure of Bayes Filter:** 
**Simplified procedure of Kalman Filter:**    
1). From control predict next state.
2). Receive measurement from 
****    
        
        ****    
        
