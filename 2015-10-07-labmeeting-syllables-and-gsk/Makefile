# Makefile for Beamer presentations

MAIN = main
FIGS = 

CLEANUP = *.aux *.dvi *.nav *.out *.snm *.toc *.log $(MAIN).ps *.bak

TEX = latex
MKPS = dvips
MKPDF = ps2pdf
#SHOW = acroread
SHOW = okular

#show:	$(MAIN).pdf
#	$(SHOW) $(MAIN).pdf
#	@echo "Close (^W) previous copies of this presentation in Acroread."

# Why don't these work???
.dvi.ps:
	$(MKPS) $<

.ps.pdf:
	$(MKPDF) $<

.tex.dvi:
	$(TEX) $<
	$(TEX) $<


$(MAIN).pdf:	$(MAIN).ps *.eps
	$(MKPDF) $<


clean:
	rm $(CLEANUP)

cleaner:	clean
	rm *.pdf

main.dvi:	main.tex

killshow:
	kill `ps auxw | grep "$(SHOW)" | awk '{ print $$2 }' | head -1`

$(MAIN).toc:	$(MAIN).tex
	$(TEX) $<

$(MAIN).ps:	$(MAIN).dvi
	$(MKPS) $<

$(MAIN).pdf:	$(MAIN).ps
	$(MKPDF) $<

$(MAIN).dvi:	$(MAIN).toc $(MAIN).tex
	$(TEX) $(MAIN).tex

.NOEXPORT:


# DO NOT DELETE
