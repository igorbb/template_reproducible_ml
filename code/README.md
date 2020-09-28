## Code Readme

Put the code intended to be reproducible in this folder.
 - Make sure to make a code that adheres to the [Code Checklist](../checklist/code.md)

# About this Project/Experiment

We want to answer a few questions to guarantee that basic documentation about code/experiment is available. We recommend you answer these questions if forking this template.

Who is doing this?

```
Igor Barros Barbosa
```

What is the purpose of this project?

```
Showcase a simple proof-of-concept of reproducible code.
The proof-of-concept is that NumPy sampler can get the same random number while running reproducible code.
```

What is the Hypothesis of the experiment/project?

```
That mybinder, docker and conda can be used to showcase reproducibility of the NumPy sampler over the browser (or locally).
```

What is the expected prediction?

```
That the x variable for the submitted code (written in a local machine), will have the same value if the code is executed at mybinder.
```

What is the hardware specification?

```
No specific hardware limitation is known. 
Supposedly machine capable of opening the mybinder link.
```

Are there any hyperparameters?

```
Yes. The sampler seed. It has been hard-code to zero.
```

Is the code open-source?

```
Yes, as defined in [License](../LICENSE)
```

What is the protocol to Run the code?


    Use [binder]((#binder)) to run a jupyter notebook server
    Jump to `code/POC.ipynb` to run the code and verify the result.
    
    Run each cell of `code/POC.ipynb` by pressing the play button




What is the table of results ?
```
x = 0.5488135039273248
```