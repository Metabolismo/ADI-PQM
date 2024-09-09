TARGET = 099-articolo-musica-tecnologia

LATEX = pdflatex
BIBTEX =  bibtex
LATEX_FLAGS = -interaction=nonstopmode -halt-on-error

OUTPUT = $(TARGET).pdf
AUXFILES = $(TARGET).aux $(TARGET).bbl $(TARGET).blg $(TARGET).log $(TARGET).toc $(TARGET).lof $(TARGET).lot

.PHONY: all clean

all: $(OUTPUT)

$(OUTPUT): $(TARGET).tex
	$(LATEX) $(LATEX_FLAGS) $(TARGET).tex
	$(LATEX) $(LATEX_FLAGS) $(TARGET).tex

$(TARGET).bbl: $(TARGET).bib
	$(LATEX) $(LATEX_FLAGS) $(TARGET).tex
	$(BIBTEX) $(TARGET)
	$(LATEX) $(LATEX_FLAGS) $(TARGET).tex
	$(LATEX) $(LATEX_FLAGS) $(TARGET).tex

clean:
	rm -f $(OUTPUT) $(AUXFILES)
