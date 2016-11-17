---
layout: post
title: Building Energy Simulation, Getting Started
modified: 2016-11-17
category: blog
tags: [python, project]
---

On my random search through repositories on Github, I stumbled upon a repository called 'SimpleBuilding' which is described as a lightweight building performance simulation engine designed to predict heating and cooling. The focus is on multi-zone commercial buildings. The code was built on a [simplified dynamic hourly method][1] from the International Standards Organization and from a PhD thesis of one [Stephane Bertagnolio][2] from University of Liège in Belgium.

It caught my interest and I decided to poke through the code and understand what is required to do the simulation. My aim is to slowly recreate the re-construct the engine while understanding the thought process of the original author. Hopefully, we discover some new and interesting information from the code that is useful in the future. You can follow my repository, comment and/or contribute to it [here](https://github.com/vignkri/SimpleBuilding).

If you find anything that can be done better. Do not hesitate to drop me a line through Github, I'll be super stoked to go through it. 

## Getting Started

Let us hit the ground running. Once forked the repository, the first step I had to do was change the code from Python-2 to Python-3.5. This was partially easy since most of the code was readily portable. Once I cleaned up the syntax and fixed all the print statements, I created a virtual-environment and froze the python package requirements file to make sure all packages are covered. 

Let's get an overview of the structure of the project:

- SimpleBuilding/
    - BESTTEST_DATA.xls
    - LICENSE
    - README.md
    - Requirements.txt
    - sbefunctionlib.py
    - SimpleBuildingEngine.py

As you might have guessed it, the three main files for the system are the besttest_data excel file, SimpleBuildingEngine and sbefunctionlib being the two script files. The `sbefunctionlib.py` file is the library of functions utilized to do the simulation of the building and the `SimpleBuildingEngine.py` being the main driver program. To augment the simulation, the `xls` file consists of the weather information that is required for some aspects of the program. 

The license file and the readme file are fairly standard. I added the requirements file which did not exist in the original repository.

## Driver flow

Great, now knowing what the folder contains, the next step is to build a simple and concise algorithm of what the simulation-driver script does. In this case, the `SimpleBuildingEngine.py` file. Thankfully, it had pretty clear sections that quickly help me draw up a simple flow:

- **IMPORT** python packages and simple-engine library
- **INITIALIZE** variables and simulation boundaries.
- **DEFINE** parameters and data for simulation including fluid, climate, weather, wall characteristics and internal gains.
- **WHILE WITHIN BOUNDARIES DO**
    - Generate humidity ratio
    - Clear sky radiation
    - Ventilation and Infiltration computation
    - Walls and solar gains
    - Node temperatures
    - Heating and Cooling
- **OUTPUT** total heating, cooling and visualizations

## Onwards!

On the next post, I'll cover the detailed flow chart of the simulation engine. This will help us provide the complete picture on what makes a lightweight building energy simulation model. Let's figure out how this works!!

[1]: http://www.iso.org/iso/catalogue_detail.htm?csnumber=41974 "ISO 13790-2008, Energy Performance of Buildings -- Calculation of Energy Use for Space Heating and Cooling, International Standards Organization, 2008."
[2]: http://ulg.academia.edu/StephaneBertagnolio "Stephane Bertagnolio's Research Page at the Thermodynamics Laboratory at the University of Liege, Belgium from his time as Post-Doctoral Researcher."
