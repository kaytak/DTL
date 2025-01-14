# DWSIM Standalone Thermodynamics Library (Dot Net Core version)

## Memo for Migration to Dot Net v6.0
This forked repository is DTL which is complied with Dotnet v6.0.
Thanks to good compatibility between Dotnet v6.0 and Dotnet framework v4.x, DTL library could be compiled on Dotnet v6.0 with minimum modification to its source code. This forked repository demonstrates the possibility to migrate DWSIM on the Dotnet v6.0 and later version. In general, Dotnet v6.0 has better performance than Dotnet framework v4.x, so it is recommended to migrate DWSIM into Dotnet v6.0/later. 
In this forked repository, some dependensy is removed since their source code is not available, however, such dependensy could be also included once they are complied on Dotnet v6.0.


Version 3.3.0.0

Copyright 2016 Daniel Medeiros

The DWSIM Standalone Thermodynamics Library is a .NET Core (or .NET 5 & later) managed dynamic link library (DLL) that exposes DWSIM's thermodynamics engine to external applications using a simple programming interface. 

DWSIM Standalone Thermodynamics Library is free for commercial and non-commercial use. Read the license.txt file for more details.

## Usage

To use the library in your .NET projects, add a reference to the DTL.Core project. All calculation functions will be available in the DTL.Thermodynamics namespace, inside the 'Calculator' class.



## Methods

This library has methods to calculate:

- Single Compound Properties
- Single Phase Mixture Properties
- PT, PH, PS, PVF and TVF Equilibrium Flashes, using an algorithm of your choice (two or three phases)

Property and Equilibrium calculation functions require parameters that must be one or more values returned by GetPropPackList, GetCompoundList, GetPropList, GetCompoundConstPropList, GetCompoundTDepPropList, GetCompoundPDepPropList and GetPhaseList. They are self-explanatory, and will return values in an array of strings.

For instance, the PTFlash function requires the name of the Property Package to use, the compound names and mole fractions, temperature in K, pressure in Pa and you may optionally provide new interaction parameters that will override the ones used internally by the library. The calculation results will be returned as a (n+2) x (3) string matrix, where n is the number of compounds. First row will contain the phase names, the second will contain the phase mole fractions and the other lines will contain the compound mole fractions in the corresponding phases.

For PH, PS, TVF and PVF flash calculation functions, an additional line is returned that will contain the temperature in K or pressure in Pa in the last matrix column.
