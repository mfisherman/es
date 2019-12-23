DOCUMENT=main

FILES=*.tex 

all: $(DOCUMENT).pdf

$(DOCUMENT).pdf: $(FILES)
	rm -f pdflatex.out
	# latex $(DOCUMENT).tex 2>&1 | tee pdflatex.out
	pdflatex $(DOCUMENT).tex 2>&1 | tee pdflatex.out
	if grep -q '\\cite{' *.tex; then bibtex $(DOCUMENT); fi;
	pdflatex $(DOCUMENT).tex 2>&1 | tee pdflatex.out
	pdflatex $(DOCUMENT).tex 2>&1 | tee pdflatex.out


clean:
	rm -f *.aux *.out $(DOCUMENT).bbl *.bst *.log *.synctex.gz
	rm -f $(DOCUMENT).blg $(DOCUMENT).dvi $(DOCUMENT).vrb
	rm -f $(DOCUMENT).pdf $(DOCUMENT).toc $(DOCUMENT).lo[a,f,g,h,l,t]
	rm -f $(DOCUMENT).nav $(DOCUMENT).snm $(DOCUMENT).ps
