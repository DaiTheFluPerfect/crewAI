# CodeInterpreterTool

## Description
This tool enables the Agent to execute Python 3 code that it has generated autonomously. The code is run in a secure, isolated environment, ensuring safety regardless of the content. 

This functionality is particularly valuable as it allows the Agent to create code, execute it within the same ecosystem, obtain the results, and utilize that information to inform subsequent decisions and actions.

## Requirements

- Docker

## Installation
Install the crewai_tools package
```shell
pip install 'crewai[tools]'
```

## Example

Remember that when using this tool, the code must be generated by the Agent itself. The code must be a Python3 code. And it will take some time for the first time to run because it needs to build the Docker image.

```python
from crewai import Agent
from crewai_tools import CodeInterpreterTool

Agent(
    ...
    tools=[CodeInterpreterTool()],
)
```

We also provide a simple way to use it directly from the Agent.

```python
from crewai import Agent

agent = Agent(
    ...
    allow_code_execution=True,
)
```