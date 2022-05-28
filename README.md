# LaTeX template for Animal Care Sheet

This template is meant to create an animal care sheet to give to someone taking care of your pets during your vacation.  
The entry point of the project is template.tex, which you should check out to make any adjustments (e.g. the language is set to German by default to mess with you).  

## Create LaTeX document
### Basics
Independant of the specific mechanism, these steps are executed:
```
	pdflatex -halt-on-error -interaction=errorstopmode -shell-escape -synctex=1 -output-directory=output template
	biber output/template
	makeglossaries -d output template
	pdflatex -halt-on-error -interaction=errorstopmode -shell-escape -synctex=1 -output-directory=output template
	pdflatex -halt-on-error -interaction=errorstopmode -shell-escape -synctex=1 -output-directory=output template
```
### Windows Batch
There is a file in folder misc named make.bat, you can execute this to generate the PDF independant of your IDE (pdflatex must be in PATH).
### Linux/MacOS makefile
The misc folder also contains a makefile you can run for the same effect.

### IDE
There are many IDEs for LaTeX. I created this fork because I wanted to use Visual Studio Code with Extension "LaTeX Workshop" an the LaTeX setup "TeX Live".  
If you want to do the same, you need to edit the settings of the Extension and set the value of "latex-workshop.latex.outDir" to "%DIR%/output". The project can then be built with "latexmk (default)". Saving any file in the project will then trigger all files to be saved, the PDF being created and the preview being refreshed.
## Credits
Based on [tammon/akad-vorlage](https://github.com/tammon/akad-vorlage), itself based on [derdanu/akad-vorlage](https://github.com/derdanu/akad-vorlage).  
Large parts were deleted so it doesn't really resemble any of the two anymore, but this explains the remnants of German comments, sorry about that. And why it goes a bit overboard in some places, like a glossary and bibliography for a Care Sheet??  
