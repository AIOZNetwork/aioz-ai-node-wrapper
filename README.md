
[![Generic badge](https://img.shields.io/badge/python-3.10-blue.svg?logo=python)](https://www.python.org/downloads/release/python-360/)
[![Generic badge](https://img.shields.io/badge/celery-5.3.1-green.svg?logo=celery)](https://docs.celeryq.dev/en/stable)
[![Generic badge](https://img.shields.io/badge/pyinstaller-6.0.0-blue.svg)](https://www.pyinstaller.org/)

# AIOZ AI NODE WRAPPER

## Abstract
`aiozAiNodeWrapper` is a specialized command-line tool for managing and operating AIOZ AI Nodes on a personal computer. This tool provides a communication layer that allows for flexible configuration of the working directory, storage limits, service ports, and synchronous connection to the AIOZ Network.

Currently, `aiozAiNodeWrapper` is released as a standalone binary, supporting four major operating system platforms:
- Linux (x86_64)
- Windows (x86_64)
- MacOS Apple (arm64)
- MacOS Intel (x86_64)

Main objectives:
- Easily check node information (storage, version, configuration)
- Launch nodes with flexible configuration

## Installation and Launch Guide

### Grant execution authority
Before launching it for the first time, you need to grant execute permissions to the binary file:
```
chmod +x aiozAiNodeWrapper
```

###  Command-line parameters (Arguments)

Some args:
- `-wd`: Set working directory (default: `~/.cache/aioz.ai.node`).
- `-dc`: Maximum allocated disk capacity in MB, example: 15360.
- `-p`: Local server port (default: 1111).
- `-i`: Display current node information.
- `-v`: Display the current version of the wrapper file.
- `--node_info`: Retrieve node information from the Server.
- `--balance`: Retrieve the current wallet balance associated with the node.
- `--withdraw`: Withdraw available balance to the registered wallet.
- `--storage`: Retrieve current storage configuration and usage of the node from the Server.
- `--update_storage`: Update allocated storage capacity for the node.
or use "--help" for more information

### Operational example
Quick check of node status and storage capacity:

```
./aiozAiNodeWrapper -wd ~/.cache -i
```

Output:
```
{
    "storage_min": 2000000000.0, 
    "storage_dir": "~/.cache", 
    "storage_limit": 15000000000.0, 
    "storage_used": 14136.0, 
    "version": "2.x.x"
}
```
Explanation:
- `storage_min`: Minimum required storage space (bytes)
- `storage_dir`: Current storage directory
- `storage_limit`: Allowed storage limit (bytes)
- `storage_used`: Used storage space (bytes)
- `version`: AINode version

Run Node with default configuration:

```
./aiozAiNodeWrapper -dc -1 -wd ~/.cache -p 1111
```
NOTE: When transmitting `-dc -1`, it is considered as not providing capacity to the node.

# License

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/">
  <img alt="License Creative Commons " style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" />
</a><br />
This repo is shared with terms of 
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/">
  Creative Commons Attribution 4.0 International (CC BY 4.0)
</a> @ <a rel="author" href="https://ai.aioz.io/"> AIOZ Pte Ltd </a>