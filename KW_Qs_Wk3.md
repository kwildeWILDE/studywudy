# Kendall's Questions Wk3 
1. In Lee et al., 2025 there is discussion on multiple regression models. When it comes to projects that are relating extreme weather events to wind turbine overloading here at the lab; what is the regression model that is used the most and why? 
    - Random forest model is the model that is currently used in ALEX projects

2. Similar to the papers by Lee et al., has there been an effort by NLR to quantify and make an algorithm to find magnitude of storm features the is mostly responsible for power outages in local regions? 
    - The ALEX group is the only* current project that uses a similar idea/study

3. From last week's discussion about the Reynold's number in terms of the Navier-Stokes equations. Since we now know that the Reynold's number can be derived from the Navier Stokes equation. How does this relate to the Reynold's Decomposition number again? 
    - Look at Pope's Reynold's Decomposition number defintion
    - Through chapters 3 & 4 of Pope's 2000, Turbulent Flows textbook, through an understnading of probability density functions (p.d.f) being uses as a tool to understand and derive an equation that allows us to map the qualties of the atmospheric momentum and thermodynamic profiels into a matrix field. 
        - i.e., "The quanties from the Navier-Stokes equation that govern the underlying turbulent velocity field." (Pope, 2000)
        Where: U(x,t) --> Specified componet of velocity at a specified position 'x' and time 't'
        - Therefore to get an equation to represent the velocity fiel U(x,t) into the mean velocity <U(x,t)> give us the follwing **fluctutating velocity field**
            - u(x,t) = U(x,t) - <U(x,t)> 
            **THIS IS THE REYNOLDS DECOMPOSITION**
        With the equation above, you can simplify equation and sub into the mean momentum equation that can eventually lead to an equation that looks very similar to the Navier-Stokes equatoin, aka **THE REYNOLODS EQUATIONS** 
            **HOWEVER** Even though The Reynolds equations and Navier-Stokes look similar and are equations that help determine turbulent or laminar flow, the **CRITICAL** difference is that the Reynolds equation take the **REYNOLDS STRESSORS** <uiuj> into consideration. 
        - Since we now have a relationship between the reynolds decomposition and its similaraties to Navier-Stokes there is a possability the the Reynolds decomposition could be derived to find a magnitude values of the Reynolds number to determine the characteristic number of the flow. 
            - The Reynolds number should be known prior before applying ANY equations related to atmospheric turbulence. 
                - i.e., Similar to how you need to know the calculation of the Reynolds number to determine how fast is the flow, how large is the domain, what is the fluid [density?].

4. In your 2025 NLR Tech Report about ASSIST + TROPoe for the linear, one-diemsional, gaussian example I understand how you were able to extend the orginal OE theorem into consideration of prior mean standard deviation and the linear calibration standard deviation (4.3); But I'm a bit confused on how you were able to get (4.4) by maximixing the left-hand side to get the most probable state condition on the observation. I think I might need to see an example of how that was done.   
    - Get more familiar with the p.d.f in satistics and the Monte Carlo in Gaussian functions 

# Things to look at: 
- ~~Boussinesq approximation~~
- ~~Pope's Reynold's Decomposition~~
- ~~p.d.f. --> with Gaussian fuctions~~
- ~~Monte Carlo ~~
- Wind farm optimization
 
