# Type 201
Super simple custom hydronic Heater/Cooler Type for TRNSYS Simulation Studio. Written in Fortran. To be used as an add-on extension for TRNSYS Simulation Studio. Either use the pre-compiled DLLs or modify the source code to your needs and then compile it yourself. 

## Purpose
Type 201 is a versatile TRNSYS component designed for simulating a heating/cooling element in thermal systems. It dynamically adjusts its output based on flow rate and temperature conditions, making it useful for simulations involving variable operational conditions.

## Key Points
- Heating or Cooling: Determines whether to heat or cool based on average fluid temperature compared to design temperature.
- Energy Calculation: Calculates energy transferred (either as heat or cooling) based on mass flow rate, specific heat capacity, and temperature difference.
- Adaptive Response: Adjusts outlet temperature and energy output based on the current operational conditions compared to nominal conditions.

## Getting started 
These instructions will get you a copy of the project up and running on your local machine.

### Prerequisities
- TRNSYS v.18 

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
5. Feel free to make any changes in the source code as desired for your project.
6. Compile the workspace by pressing Ctrl+B or by selecting the Compile Workspace button under the Build menu.
7. Launch TRNSYS Simulation Studio. You'll see a directory named HeaterCooler(CUSTOM) in the library tree on the right-hand panel. Inside this directory, Type201 will be available.
8. Now, you're all set! Use it just like you would with other Types.

## Usage
Type 201 simulates a heating or cooling element, which adjusts the temperature of a fluid (by default water) based on various parameters and inputs.
### Parameters
- Qn: Nominal heating/cooling power (kJ/hr).
- Mw_n: Nominal mass flow rate of the fluid (kg/hr).
- Tw_1n, Tw_2n: Nominal inlet and outlet temperatures of the fluid (°C).
- cp: Specific heat capacity of the fluid (kJ/kg.K).
- T_Dn: Nominal design temperature (°C).
### Inputs:
- Tw_1: Inlet temperature of the fluid (°C).
- T_D: Design temperature (°C).
- Mw_in: Inlet mass flow rate (kg/hr).
### Outputs:
- Qheat: Heat output (kJ/hr).
- Tw_2: Outlet temperature (°C).
- Qcool: Cooling output (kJ/hr).
- Mw_out: Outlet mass flow rate (kg/hr).

## Functionality
### Initial Checks
The component begins by checking the validity of parameters and inputs, ensuring positive flow rates and power values.
### Calculation Logic
The model first checks if the flow rate (Mw_in) is below a certain threshold (36 kg/hr). If so, it assumes no flow, sets heating/cooling output to zero, and maintains inlet temperature as the outlet temperature.
If the flow rate is above the threshold, it calculates whether the system should heat or cool based on the average temperature (Tw_m) compared to the design temperature (T_D).
Depending on whether heating or cooling is needed, it calculates the outlet temperature (Tw_2) and the respective heating (Qheat) or cooling (Qcool) output.
The calculations involve the nominal parameters, the specific heat capacity, and the inlet and design temperatures.

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
## Authors:
- [x] Bořivoj Šourek (ČVUT UCEEB) - mathematical model
- [x] Erika Langerová (ČVUT UCEEB) - Fortran implementation

## License 
This project is licensed under the LICENSE.md - see the file for details.
 
