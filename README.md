# Type201
Super simple custom hydronic Heater/Cooler Type for TRNSYS Simulation Studio. Written in Fortran. To be used as an add-on extension for TRNSYS Simulation Studio. Either use the pre-compiled DLLs or modify the source code to your needs and then compile it yourself. 

## Getting started 
These instructions will get you a copy of the project up and running on your local machine.

### Prerequisities
- TRNSYS version v.18 

### Installation
1. Clone the repo or download the source files
   
  ```bash
  git clone https://github.com/langeeri/Type201.git
```
---  
#### If you want to use the pre-compiled DLLs
---
1. Navigate to the cloned project directory

   ```bash
   cd [path-to-the-cloned-repo]
   ```

3. Move all files from the `UserLib\DebugDLLs` and `UserLib\ReleaseDLLs` directories to their corresponding directories in the TRNSYS root directory (default location: `C:\TRNSYS18`).
4. Move all files from the `Studio\Proformas` directory to the corresponding directory in the TRNSYS root directory.
5. Launch TRNSYS Simulation Studio. You'll see a directory named HeaterCooler(CUSTOM) in the library tree on the right-hand panel. Inside this directory, Type201 will be available.
6. Now, you're all set! Use it just like you would with other Types.
---  
#### If you want to modify the source code and compile yourself
---
> [!CAUTION]
> We strongly recommend compiling the source code exclusively through TRNSYS TypeStudio (TRNSYS embedded compiler).
> 
1. Navigate to the cloned project directory

   ```bash
   cd [path-to-the-cloned-repo]
   ```
2. Move all files from the `SourceCode\` directory to the corresponding directory in the TRNSYS root directory (default location: `C:\TRNSYS18`).
3. Move all files from the `Studio\Proformas` directory to the corresponding directory in the TRNSYS root directory.
4. Launch TypeStudio.exe (default location: C:\TRNSYS18\TypeStudio). Load the source code you copied in Step 2 into TypeStudio.
5. Feel free to make any changes in the source as desired for your project.
6. Compile the workspace by pressing Ctrl+B or by selecting the Compile Workspace button under the Build menu.
7. Launch TRNSYS Simulation Studio. You'll see a directory named HeaterCooler(CUSTOM) in the library tree on the right-hand panel. Inside this directory, Type201 will be available.
8. Now, you're all set! Use it just like you would with other Types.

## Usage

## Versioning
This project follows Semantic Versioning (SemVer), which means the version number is structured as MAJOR.MINOR.PATCH.

- [x] MAJOR version: Increased for incompatible changes to the TRNSYS Type structure or behavior.
- [x] MINOR version: Incremented for the addition of new features while maintaining backward compatibility.
- [x] PATCH version: Incremented for backward-compatible bug fixes or improvements.

You can find the list of all available versions or releases for this project in the tags section. 

> [!TIP]
> We use Git tags to mark each release. For example, to check out version 1.0.0, you can use the following command:
   ```git
  git checkout tags/v1.0.0
   ```

## License 
This project is licensed under the LICENSE.md - see the file for details.
 
