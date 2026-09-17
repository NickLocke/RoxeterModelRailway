# Environment Configuration

## Github

Each library is held in a separate Git repository, with names such as `Library-RoxXxxxxx`. There is also a separate repository `Roxeter` for the core application code. S Code has to be instructed not to include the library folders in the core repository. That is accomplished by including the list of library folder names in the `.gitignore' file of the core repository.

## Platform IO

Rather than using the Arduino IDE, the Visual Studio Code add in Platform IO has been adopted. That decision was taken because Platform IO gives more flexibility in terms of being able to work on multiple projects/libraries at the same time. It also supports loading code to the Pico and using the Serial Monitor. There are some quirks in the setup process though, so those have been documented as far as possible. That documentation can be found [here](PlatformIo.md).

## C++ Code

This is not intended to be a full description of the C++ language. However, teh learning curve has been quite steep and the same issues tend to be encountered many times. [This section](CPlusPlusCode.md) of the documentation is intended to give a quick reference for those issues.