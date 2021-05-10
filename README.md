# Debian Package CPack Template

This project contains a [CPack](https://cmake.org/cmake/help/latest/module/CPack.html) template to build a [Debian package](https://wiki.debian.org/Packaging) of external third-party [CMake](https://cmake.org/) projects.
This project is created to simplify the deployment of third-party libraries/frameworks which are build using CMake but do not yet have an official Debian package to be used.
This project works by including a third-party source code as a [Git submodule](https://git-scm.com/book/en/v2/Git-Tools-Submodules), then including it as a [CMake subdirectory](https://cmake.org/cmake/help/latest/command/add_subdirectory.html), and last compile it as a Debian package.

## Usage

### Including the Third-party Source Code

- Clone the third-party source code repository as a Git submodule.
  ```bash
  $ git submodule add https://github.com/user/something
  ```
  > Optionally, you could specify the branch/tag to be used using `-b` option, see [this](https://git-scm.com/docs/git-submodule#Documentation/git-submodule.txt--bltbranchgt).
- If the Git submodule already exists, initialize it and pull the latest commits.
  ```bash
  $ git submodule update --init --recursive
  ```
- Modify the CPack configuration in the [CMakeLists.txt](./CMakeLists.txt) according to the current third-party source code information.
  > See [this guide](https://cmake.org/cmake/help/latest/cpack_gen/deb.html) for more information on CPack configuration for Debian package.

### Building the Project

- Create a build directory and move to it.
  ```bash
  $ mkdir build
  $ cd build
  ```
- Configure the CMake with the following options.
  ```bash
  $ cmake -DCMAKE_INSTALL_PREFIX=/usr ..
  ```
- Build the project.
  ```bash
  $ make
  ```
  > Optionally, you could speed up the build process by specifying the parallel job using `-j` option, see [this](https://www.gnu.org/software/make/manual/html_node/Parallel.html).
- Create the Debian package using CPack.
  ```bash
  $ cpack
  ```

## License

This project is maintained by [Alfi Maulana](https://threeal.github.io/) and licensed under the [MIT LICENSE](./LICENSE)
