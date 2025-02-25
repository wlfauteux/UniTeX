<div align="center">

# UniTeX

UniTeX is a collection of scientific oriented and minimalistic [LaTeX](https://www.latex-project.org/) templates suitable for many assignment types.

![LaTeX](https://img.shields.io/badge/latex-%23008080.svg?style=for-the-badge&logo=latex&logoColor=white) ![Shell Script](https://img.shields.io/badge/shell_script-%23121011.svg?style=for-the-badge&logo=gnu-bash&logoColor=white) ![Overleaf](https://img.shields.io/badge/Overleaf-47A141?style=for-the-badge&logo=Overleaf&logoColor=white)

![LICENSE](https://img.shields.io/github/license/wlfauteux/UniTeX?color=blue&style=for-the-badge) ![release](https://img.shields.io/github/v/tag/wlfauteux/Unitex?color=%23FF7F50&style=for-the-badge)

</div>

# Table of contents

[Getting started](#getting-started)

[Configuration](#configuration)

[Local LaTeX installation](#local-latex-installation)

[Todo](#todo)

# Getting started

The simplest way to use UniTeX's templates is by dowloading one from the links below

<div align="center">

|   Template   	|                                                                                                                    Description                                                                                                                    	| See template                                                                       	| Download link                                                                                                         	|
|:------------:	|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:	|------------------------------------------------------------------------------------	|-----------------------------------------------------------------------------------------------------------------------	|
|    Classic   	| Most likely suits longer document style such as lab and internship reports. 	| [See default](https://github.com/wlfauteux/UniTeX/blob/main/classic/main.pdf)      	| [Get classic](https://downgit.evecalm.com/#/home?url=https://github.com/wlfauteux/UniTeX/tree/main/classic)           	|
|  Homework  	| Useful for homework assignments or projects that needs clear split between uncorrelated sections.                                            	| [See default](https://github.com/wlfauteux/UniTeX/blob/main/homework/main.pdf)     	| [Get assignment](https://downgit.evecalm.com/#/home?url=https://github.com/BCarnaval/UniTeX/tree/main/Assignment)         	|
| Presentation 	| Beamer presentation style. Very minimalistic.                                                                                                                                                                                                     	| [See default](https://github.com/wlfauteux/UniTeX/blob/main/presentation/main.pdf) 	| [Get presentation](https://downgit.evecalm.com/#/home?url=https://github.com/wlfauteux/UniTeX/tree/main/presentation) 	|

</div>

You can directly use the downloaded within [Overleaf](https://www.overleaf.com/) by selecting `New project > Upload project > Select a .zip file`.

To use it locally, UniTeX requires a complete TeX distribution. Most features need external tools such as latexmk that fully automates LaTeX document generation. Latexmk is usually part of TeX distributions like MikTeX and MacTeX but you can always install it separately by following [these](https://mg.readthedocs.io/latexmk.html) steps.

## Suggestion for Homework and Classic template Users

Before you start using these templates, it is HIGHLY recommended to go over key packages located in `style.sty` and user defined commands located in `commands.sty`. Here are some of the many packages which should be read before your debut, as they'll only help you become more efficient.
- `siunitx`: Internation System of Units implementation for LaTeX documents.
- `physics`: Physics and mathematics command shortcuts for some of THE most used operators (e.g. derivative, partial derivative, matrices, Dirac's bra-ket notation).
- `amsmath`: American Mathematical Society package for mathematics.

Of course, they should not be read in their entirety but they SHOULD be looked at just enought for you to get a grasp of what they can do.

# Configuration

Every template folder contains a `main.tex` file in which are inputed configuration files (`preamble.sty, style.sty, commands.sty` and `colors.sty`) and the `.tex` files of the different sections of the project. Here we will describe how you can personnalise the template using the variables in these files.

### Classic

- `main.tex`: use this file to change the color of the document details by changing the value of `MasterColor` variable for one listed in [colors.sty](https://github.com/wlfauteux/UniTeX/blob/main/classic/colors.sty). Title page variables are also at the beginning of this file.
- `colors.sty`: use this file to choose a color for you document! If you want a color that is not listed in the file, add it by yourself using the same format.
- `style.sty`: This is where all the modules are imported and briefly commented. Then, the style is defined (TOC setting, headers, references, dimensions, titles and etc.).
- `commands.sty`: This is the place to defined your own commands. I put some for math & physics as well as the custom colored boxes.

### Homework

- `main.tex`: use this file to change the color of the document details by changing the value of `MasterColor` and `MinorColor` (lighter than principal color for the filling of the section box) variables for one listed in [colors.sty](https://github.com/wlfauteux/UniTeX/blob/main/homework/colors.sty). Title page variables are also at the beginning of this file.
- `colors.sty`: use this file to choose a color for you document! If you want a color that is not listed in the file, add it by yourself using the same format.
- `style.sty`: This is where all the modules are imported and briefly commented. Then, the style is defined (TOC setting, headers, references, dimensions, titles and etc.).
- `commands.sty`: This is the place to defined your own commands. I put some for math & physics as well as the custom colored boxes.

### Presentation

- `premable.sty`: Beamer theme and color are defined here. Same for used modules and style settings. I regrouped all of the configuration files in one because of the simplicity of the project.

# Local LaTeX installation

You can find the most used TeX distributions [here](https://www.latex-project.org/get/#tex-distributions). In my experience, [TeX Live](https://www.tug.org/texlive/) and [MiKTeX](https://miktex.org/) are the most reliable and easy to use out-of-the-box.

> [Latexmk](https://www.cantab.net/users/johncollins/latexmk/) is usually part of TeX distributions like MikTeX and MacTeX but you can always install it separately by following [these](https://mg.readthedocs.io/latexmk.html) steps. It is essential if you want to use the Makefiles.

Each UniTeX template contains a `Makefile` in which are defined very useful commands if you plan to compile the templates locally. For example, using

```shell
make
```

at the root of a template will start a continuous compilation with `latexmk` and will update itself when you modify any of the project's file. The possible commands are

- `make clean`: Cleans the project's folder from garbage files (.bbl, .synctex, .aux, etc.)
- `make dry`: Compiles the project but non-contiuously
- `make zip`: Compiles the project then build a .zip with it.
- `make targz`: Compiles the project then build a .tgz with it.

