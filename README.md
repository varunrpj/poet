# POET and Enhanced POET

This repo contains implementation of the POET and Enhanced POET algorithms described in:

[Paired Open-Ended Trailblazer (POET): Endlessly Generating Increasingly Complex and Diverse Learning Environments and Their Solutions](https://arxiv.org/abs/1901.01753)

[Enhanced POET: Open-Ended Reinforcement Learning through Unbounded Invention of Learning Challenges and their Solutions](https://arxiv.org/abs/2003.08536)

An article on Uber Engineering Blog describing POET can be found [here](https://eng.uber.com/poet-open-ended-deep-learning/).

## Requirements

- [Fiber](https://uber.github.io/fiber/)
- [NEAT-Python](https://neat-python.readthedocs.io/en/latest/installation.html)
- [OpenAI Gym](https://github.com/openai/gym)

Changes to make to code before running:
- In ```poet/poet_distributed_niches/box2d/bipedal_walker_custom.py```, change all instances of ```randint(<arguments>)``` to ```integers(<arguments>)```.
- When downloading Python libraries, use ```sudo pip install <library>``` rather than simply ```pip install <library>```.

## Run Enhanced POET locally

To run locally on a multicore machine

```./run_poet_local.sh final_test```

## Run Enhanced POET on a Kubernetes cluster

Follow instructions [here](https://uber.github.io/fiber/advanced/#working-with-persistent-storage) to create a persistent volume.

Then run the following command:

```./run_poet_remote.sh final_test```

To get the training logs:

```fiber cp nfs:/persistent/logs/final_test .```
```fiber cp nfs:/persistent/logs/poet_final_test poet_final_test```

## Run Enhanced POET on a computer cluster

To containerize and run the code on a computer cluster (e.g., Google Kubernetes Engine on Google Cloud), please refer to [Fiber Documentation](https://uber.github.io/fiber/getting-started/#containerize-your-program).

## Run original POET

Use this [legacy branch](https://github.com/uber-research/poet/tree/original_poet)
