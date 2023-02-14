SHELL=/bin/bash
THESIS=thesis

.SUFFIXES:
.SUFFIXES: .bib .pdf .tex
.PHONY: clean

run: $(THESIS).pdf


$(THESIS).pdf: $(THESIS).tex
	pdflatex $(THESIS).tex -draftmode
	pdflatex $(THESIS).tex 
	cp $(THESIS).pdf ../Ausarbeitung_Modularer_Synthesizer.pdf
	rm $(THESIS).pdf

$(THESIS).bbl: $(THESIS).aux
	bibtex $(THESIS).aux

$(THESIS).aux: refs.bib
	pdflatex $(THESIS).tex -draftmode
	pdflatex $(THESIS).tex -draftmode

clean:
	rm -f *.{aux,lof,log,lot,lol,,bcf,toc,bbl,blg,run.xml,out}
	rm -f content/*.{aux,lof,log,lot,lol,,bcf,toc,bbl,blg,run.xml,out}
