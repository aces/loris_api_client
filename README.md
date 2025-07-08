# LORIS Python API client

## Description

This repository contains the LORIS Python API client, a Python client to interact with the LORIS public HTTP API.

## Installation

To install this project, use the following command:

```sh
pip install git+https://github.com/aces/loris-python-client.git@26.0
```

## Example

To use the LORIS Python API client, use the `LorisApiClient.connect` method to connect to the API and pass the client to the desired endpoints.

```py
from loris_api_client.client import LorisApiClient
from loris_api_client.endpoints.visit import try_get_candidate_visit

client = LorisApiClient.connect('https://demo.loris.ca', 'username', 'password')

candidate = 'DCC060'
visit     = 'V1'

candidate_visit = try_get_candidate_visit(client, candidate, visit)
if candidate_visit is not None:
    print(f"Candidate {candidate} exists and has visit {visit} for project {visit.meta.project}.")
else:
    print(f"Candidate {candidate} does not exist or has no visit {visit}.")
```

## Documentation

This repository unfortunately does not have much documentation, however, you can always refer to the type hints or the LORIS API documentation for instructions. Do not hesitate to open an issue or PR if needed.
