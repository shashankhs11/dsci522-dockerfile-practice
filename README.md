# dsci522-dockerfile-practice

## Individual Assignment 2

Step 1: Create environment.yml file

```python
# environment.yml
name: docker-practice
channels:
  - conda-forge
  - defaults
dependencies:
  - pandas=2.2.2
  - pandera=0.20.4
  - python=3.11
  - pip
  - pip:
    - deepchecks==0.18.1
```

Step 2: Run the below command. This creates the `conda.lock` file

```bash
conda-lock --kind explicit --file environment.yml -p linux-64
```
Step 3: Create a new `Dockerfile` and use the below command to build
`testing_cmds` is the name of the docker image. Make sure to add the platform tag

```bash
docker build --platform=linux/amd64 --tag i_assignment_2 .
```

Step 4: Run the docker image after building

```bash
docker run --rm -it i_assignment_2 /bin/bash
```

