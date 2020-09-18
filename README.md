# nrf52-project-template

This template uses submodules! You'll need a recursive clone.

Template to start a new nrf52 project with the AWS IoT SDK. It is intended to be used in Visual Studio Code with at least this extensions:

- C/C++
- C++ Intellisense
- Cortex Debug

It is also recommended to install `Tasks` in order to have more convenient access to the configured tasks.

## Configuration

### Env vars

You need to set some env vars:

- `GNU_GCC_ARM`
- `GNU_GCC_ARM_LIBS`
- `nRF_SDK`

I'm using the .bashrc to make sure that the vars are always set when I launch Visual Studio. There is an example of my values in `.vscode/sdk_routes_config.sh.example`.

## Folders

- `/boards`: Makefile, .ld file and sdk_config.h file for the possible targets (only nrf52//PCA10056 for now).
- `/build`: Intended for build output.
- `/project`: Your code goes here.
- `/secrets`: To store passwords and certificates (git will ignore it).

## ToDo

### Add support for Mac and Windows

At least two files would need to be updated to fully support Windows and Mac:

- `.vscode/settings.json`: The correspondent shell args line would need to be added, possibly a new script too.
- `.vscode/c_cpp_properties.json`: The correspondent configurations need to be completed.

### Add support for different target boards

Currently, only the nrf52 is supported through the PCA10056 board. New environmental variables would be needed to adapt the commands in `.vscode/tasks.json` and `.vscode/launch.json`.
