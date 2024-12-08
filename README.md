# Temporal: Bulletproof Workflows

## Step 1/4: Installation
### Install Temporal CLI
To install the Temporal CLI, download the version for your architecture:
- [Download Temporal CLI for Linux amd64](https://temporal.download/cli/archive/latest?platform=linux&arch=amd64)
- [Download Temporal CLI for Linux arm64](https://temporal.download/cli/archive/latest?platform=linux&arch=arm64)

For example: `temporal_cli_1.1.2_linux_amd64.tar.gz` file.

Extract the downloaded archive. Example:
```sh
$ tar xzf temporal_cli_1.1.2_linux_amd64.tar.gz
```

Add the `temporal` binary to your `PATH` by copying it to a directory like `/usr/local/bin/`.
Example:
```sh
$ mv temporal /usr/local/bin/
```
### Install Temporal SDK
Install the Temporal Python SDK:
```sh
$ pip install temporalio
```

## Step 2/4: Start Temporal Server
Open a new terminal window and run the following command:
```sh
$ temporal server start-dev
```

This command starts a local Temporal Server. It starts the Web UI, creates the `default` [Namespace](https://docs.temporal.io/namespaces?_gl=1*c6vqdb*_gcl_au*MTIwMzc0ODY4OC4xNzMzMjU2NDU0*_ga*MTY3NTk4Mzk3MC4xNzMzMjU2NDU0*_ga_R90Q9SJD3D*MTczMzY5MjczMy45LjEuMTczMzY5MzM1My4wLjAuMA..), and uses an in-memory database.

The Temporal Service will be available on `localhost:7233`.
The Temporal Web UI will be available at http://localhost:8233.

Leave the local Temporal Server running. You can stop the Temporal Service at any time by pressing `Ctrl+C`.

## Step 3/4: Start Temporal Worker
Open a new terminal window and run the following command:
```sh
$ python3 worker.py
```
Leave the Temporal Worker running.

## Step 4/4: Execute Temporal Workflow
Open a new terminal window and run the following command:
```sh
$ python3 app.py
```

Example output:
```sh
Result: Hello World!
```

Navigate to Temporal Web UI at http://localhost:8233 to see Temporal Workflows:
![temporal-_-workflows.png](img/temporal-_-workflows.png "Temporal Workflows")

Click on `example-workflow` Workflow ID to see Temporal Workflow History and Execution Result:
![temporal-_-workflow_history.png](img/temporal-_-workflow_history.png "Temporal Workflow History")

## Sources
- [Set up a local Temporal Service for development with Temporal CLI](https://learn.temporal.io/getting_started/python/dev_environment/?os=linux#set-up-a-local-temporal-development-cluster)
