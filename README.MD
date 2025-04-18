# Pytotex

## Description 

This repository converts matplotlib plots to a latex document. Enabling the annotation of figures in an organized manner. It is not meant to generate beautiful figures, but rather keep one's plots a bit more organized.

## Components 

Currently the package is composed of three different classes. 

1. TextoFig - Helper classe the manages latex files as well as directory organization.
2. TexFig - A class which handles generating latex syntax and saving matplotlib figures in the right directory.
3. MPTexFig - A class which creates a multiple panel figure from a list of TexFig. 

### mpl2tex.TexFig() ###

Class to generate a single panel figure.

- `figure:` Takes an `mpl.Figure`
- `caption:` Longer description of data presented in figure.
- `title:` Short title used for table of contents.
- `figure_filename` Default file name is lower case title.
- `subfigure:` Boolean - default is False. 
- `output_type:` File suffix - defual is `.pdf`

```
mpl2tex.TexFig(figure, caption, title, subfigure)
```

### mpl2tex.MPTexFig() ###

Class to generate a multipanel figure.

- `figures:` List of `mpl2tex.TexFig`
- `title:` Short title used for table of contents.
- `caption:` Longer description of data presented in figure.

```
mpl2tex.MPTexFig(Figures = figures, caption, title)
```

### mpl2tex.figtotex() ### 

Function that generates and runs the methods of MPTexFig. To add figure to LaTex document.

`plot_type:` Name for type of plots (e.g. experimentA_replicate_correlations)
`figures:` List of `TexFig` or `MPTexFig`
`outpath:` Path to output directory

```
mpl2tex.figtotex(plot_type, figures, outpath)
```

## Organization of output directory 

```
output\
    inputs\plot_type.tex
    plots\plot_type\plot.pdf
    main.tex 
```
- Plots are labeled with the date. The package will not overwrite existing plots.


