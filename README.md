# Dockerfile Bug: Missing requirements.txt

This repository demonstrates a common error in Dockerfiles: attempting to copy a non-existent file.  The original `Dockerfile` attempts to copy `requirements.txt`, but this file is missing from the build context.  This results in a build failure.

The `Dockerfile_fixed` provides a corrected version, ensuring the `requirements.txt` file is present in the build context before the `COPY` instruction.

## Steps to Reproduce the Bug:
1. Clone this repository.
2. Attempt to build the original `Dockerfile` using `docker build -t my-app .`
3. Observe the build failure due to the missing `requirements.txt` file.

## Solution:
The `Dockerfile_fixed` includes the `requirements.txt` file in the build context, resolving the build failure.