# Modelling and Simulation in Engineering

## Modelling in Engineering

Before diving into the more complex topic of digital twins, we need to strengthen our understanding of what a model is in the context of engineering. According to {cite:p}`SimulationBossel`, a model can be defined as "...a **simplified representation** of a particular domain of reality." In addition, {cite:p}`SimulationBossel` argues that "... if a model is valid, it is only for a **particular domain** and it was developed for a **particular purpose**." {cite:p}`SimulationBossel`'s definition highlights important features applicable to any engineering model. First, a model is a simplification of a real system; thus, it is not the real system itself, nor can it be considered a copy of it. This distinction is important in the context of digital twins, as (advanced physical) models are often labeled as such. A model, being a limited representation of a real (or virtual) system, can only reproduce a limited set of behaviours or properties of the real system. Second, different purposes require different models. The purpose of any engineering model is defined by the scope of the system or phenomenon that we are interested in studying, as well as the purpose of the particular model. This scope also defines the model's input and output information. 

### Modelling Scope and Purpose
The scope of a model determines the desired system representation, and its purpose defines and constrains its features and developments. Based on their modelling purpose, one can define four different categories of models. These are *predictive*, *prescriptive*, *descriptive*, and *conceptual*, as presented in {numref}`category-models`. We can encounter all these types of models in power systems, with descriptive and conceptual models being of greater interest, as they help us enhance our understanding of the power system's properties. Different from predictive and prescriptive models, which focus on the input $x$ and output $y$ relationship, descriptive and conceptual models are more interested in the internal structure and how different internal subsystems are interconnected and share data. Accordingly, different model categories require different data and knowledge of the system being modeled. As examples of predictive and prescriptive models, we find those based on machine learning (e.g., neural networks), usually known as black-box models, while descriptive and conceptual models are usually based on the physics of the specific behaviour being modeled and are known as white-box models. Naturally, a combination of both approaches is also available, leading to the development of hybrid models, often known as grey-box models. Each of these model categories comes with its own features and constraints. Depending on the physical phenomenon being modeled, developing predictive and prescriptive models is typically straightforward. As a result, such models are easy to validate and deploy in more complex engineering workflows and are ideal for applications that require real-time outputs. In contrast, descriptive and conceptual models require extensive knowledge and expertise to develop and often involve complex subsystems or submodels that may require significant computational resources for providing outputs, limiting their application in real-time settings. 

```{list-table} Categories of Models
:header-rows: 1
:name: category-models

* - Type
  - Description
* - Predictive
  - Determine an input that leads to a desired output (given $y$, what is $x$)
* - Prescriptive
  - Estimate the output for a given input (given $x$, what is $y$)
* - Descriptive
  - Summarise the observed behaviour of a system across its inputs and outputs (the set of $(x,y)$ pairs)
* - Conceptual
  - Improve the understanding of the system (explore the properties of $f()$, often with the intent to generalize)
```

### Models, Algorithms, and Simulators
In engineering modelling, several well-known terms come easily. To name a few, when modelling, engineers can talk about (mathematical) *equations*, *algorithms*, *solvers*, *simulators*, and *simulations*. Although they are correlated in the modelling context, and are often used interchangeably, these terms differ in meaning. When modelling a real (or virtual) system, a model is usually used to present certain behaviours. As previously discussed, and depending on the type of model used, such model can be described with mathematical *equations*. To represent the real system's behaviour with high fidelity, these mathematical *equations* require a set of parameters that must be fitted, perhaps using measured data from the real system. Next, we define an *algorithm* as the set of steps used to evaluate the developed model. Depending on its complexity, we may be required to use a computer *simulator* (that usually hosts a solver), to solve our model. Alternatively, simpler models can also be solved mathematically. Finally, the output of the *simulation* process provides some simulation results (numbers) that represent the expected system behaviour under the solved model's constraints. To better understand the relationships among models, algorithms, and simulators, {numref}`models_simulation_blocks` presents a schematic that illustrates the information and data exchange in a simulation analysis setup. 

As an example, consider the power flow model used to estimate voltage, current, and power in a power system. In this case, the set of equations that describes the relationships among voltage, current, and power constitutes the mathematical formulation underlying the power flow model. Some of this model's parameters include the resistance and reactance of lines and cables. As the power flow model is a complex, non-linear mathematical set of equations, it is required to use an algorithm to derive its solution. A classical algorithm for solving the power flow model is the iterative Newton-Raphson method, which is already deployed in a variety of commercial software packages (e.g., PowerGridModel {cite:p}`power_grid_model` or PandaPower{cite:p}`panda_power`). Simulation results obtained from the power flow model are fundamental for the day-to-day operation and planning of the electricity infrastructure. 

```{figure} ../part_1/models_simulation_blocks.png
---
height: 300px
name: models_simulation_blocks
---
Schematic representation of the information and data exchange in a simulation analysis setup. 
```
## Simulation in Engineering 







