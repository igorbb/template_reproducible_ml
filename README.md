# Template for reproducible Machine Learning.
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/igorbb/template_reproducible_ml/master)


To get started with the proposed solution for core reproducibility we use user Docker+Conda+Binder.
You can fork this template, and replace with your own solution.

To help out we propose few checklists and present a very simple project. Read more in the secction [Project Goal](#project-goal)

### Checklists
Use the following checklists to make sure your work is striving for reproducibility.

- Here is a checklist for code reproducibility : [Code](../master/checklist/code.md)
- Here is a checklist for method documentation : [Method](../master/checklist/method.md)
- If you are publishing data : [Data](../master/checklist/data.md)
- [Joelle Pineau has a great checklist for machine learning reproducibility](https://www.cs.mcgill.ca/~jpineau/ReproducibilityChecklist.pdf)


### Deep Dive   

This template repo is a simple and barebone solution. 
A better and didatic deep dive is presented in [The turing way Guide for Reproducible Research](https://the-turing-way.netlify.app/reproducible-research/reproducible-research.html)
.

# Project goal.

Here is where one should have a description of your project goal.
Bonus points if you include Hypothesis/Prediction/Concussion.

In our case, our goal is to showcase a toy example of reproducibility.
We have a code [POC.ipynb](../master/code/POC.ipynb) that was run locally. 
We believe that we can have the code achieve the same result while running on [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/igorbb/template_reproducible_ml/master)


## Reproducible run

There are three options to run this repository and check results.

They are listed below from prefered to least prefered order.
### Option 1

Use [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/igorbb/template_reproducible_ml/master) to get a running jupyter notebook.
Jump to `POC.ipynb` to run the code and verify the result.
What is the protocol to Run the code?

 - Run each cell of [POC.ipynb](https://mybinder.org/v2/gh/igorbb/template_reproducible_ml/f8453ccb532c51ea46f7be096f888d5db6951e72) by pressing the play button


### Option 2

Use docker and docker-compose.
You will need docker and docker-compose installed at your development machine.
Use the scrip `run_localy.sh` to start a jupyterlab with the environment.
Jump to `POC.ipynb` to run the code and verify the result.


### Option 3
Use conda and the provided environment, to set up things in your local computer manually.
