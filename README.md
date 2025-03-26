# Public Build Info

Although each project can be built directly using the CMake scripts,
this places the responsibility of dependency management on the project consumer.

The recommended approach is to build using [Conan 2](https://conan.io/).

The provided instructions are designed to assist external users,
especially those unfamiliar with Conan, in quickly setting up and building the projects.

## Requirements

* Conan 2.14 or newer. To install in a dedicated virtual-environment on a Linux system:
    ```bash
    # Create and activate a dedicated virtual-environment (optional)
    python3 -m venv venv-conan2
    . venv-conan2/bin/activate
    # Install latest Conan
    pip install conan
    ```
* A default profile compatible with your environment toolchain, and targeting C++20 standard.
    ```bash
    # Auto-generate a default profile if it was not already present
    conan profile detect
    # Make it target C++20 standard
    sed -i '/compiler.cppstd/d' ~/.conan2/profiles/default
    echo "compiler.cppstd=20" >> ~/.conan2/profiles/default
    ```



