# SIRModelDiscreteTimeExploration
Exploring the SI and SIR model with discrete time. I made these figures in my presentation on ShaneMcInnis's Twitch stream on May 9, 2026, where I attempt to explain the model without using Calculus.

The SIR model is a common model for the spread of disease in a population. The population is divided into three categories: Susceptible, Infected, and Recovered (or Removed), which can change over time. To understand the SIR model, it can be helpful to first learn about the SI model, where there are only Susceptible and Infected categories. For the SI model, I'm simulating the equations

$$S(t+1)-S(t)=-bS(t)I(t)+gI(t)$$

$$I(t+1)-I(t)=bS(t)I(t)-gI(t)\textrm{,}$$

where $b$ is the force of infection (probability of disease transmission per contact multiplied by average number of contacts per person) and $g$ is the recovery rate (one divided by the average infectious period). The equations being simulated for the SIR model are

$$S(t+1)-S(t)=-bS(t)I(t)$$

$$I(t+1)-I(t)=bS(t)I(t)-gI(t)$$

$$R(t+1)-R(t)=gI(t)\textrm{.}$$

As written, these equations have issues with numerical stability and it can be difficult to find parameter values that work. For more flexibility, you could use a time step $\Delta t$ smaller than one:

$$S(t+\Delta t)-S(t)=-bS(t)I(t)\Delta t$$

$$I(t+\Delta t)-I(t)=bS(t)I(t)\Delta t-gI(t)\Delta t$$

$$R(t+\Delta t)-R(t)=gI(t)\Delta t\textrm{.}$$
