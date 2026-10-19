# Introduction

In this chapter, we are going to discuss about these fundamental questions:

> What exactly are we estimating? How do we mathematically describe how the system evolves? How do sensors observe it?

These concepts are essential for understanding the Kalman Filter.

We will first discuss what the term state means, how a state is commonly represented, and how the evolution of a dynamic system can be described using a state-space model.

# What is a state?

Scientifically:

> **A state is the minimum set of variables that contains all the information needed to describe the system at a given time and predict its future evolution, given the system inputs.**

Consider a simple weather example. If we want to describe the weather at a certain moment, temperature alone may not be sufficient. Two cities may have the same temperature but different humidity, pressure, or wind conditions. Therefore, depending on what we want to predict, several variables may be needed to describe the state of the atmosphere.

Now consider a rigid body moving in a 2D plane. To describe its **pose**, we need its position $$\(x,y\)$$ and its orientation $$\(\phi\)$$. Therefore, one possible state representation is

$$
\mathbf{x}=
\begin{bmatrix}
x\\
y\\
\phi
\end{bmatrix}.
$$

The important word here is **pose**: $$\(x,y\)$$ gives the position, while $$\(\phi\)$$ gives the orientation. Together, they fully describe the rigid body's pose in a 2D plane.

# What is a state-space model?

The next natural sentence after this would be: Once the state has been defined, the next question is how this state changes over time. That leads very naturally into the **state transition model**.

A State-Space Model (SSM) is a mathematical model that describes:
- how the state evolves with time,
- how measurements are generated from that state using the sensors.

