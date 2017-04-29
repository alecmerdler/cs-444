TEX     = latex -shell-escape
DVIPS	= dvips
DVIPDF  = dvipdft
XDVI	= xdvi -gamma 4
GH		= gv

EXAMPLES = $(wildcard *.h)
SRC	:= $(shell egrep -l '^[^%]*\\begin\{document\}' *.tex)
TRG	= $(SRC:%.tex=%.dvi)
PSF	= $(SRC:%.tex=%.ps)
PDF	= $(SRC:%.tex=%.pdf)

all: writeup

writeup:
	latex report.tex
	dvips -R -Poutline -t letter report.dvi -o report.ps
	ps2pdf report.ps

turnin:
	rm -f *.ps *.dvi *.out *.log *.aux *.bbl *.blg *.pyg

clean:
	rm -f *.pdf *.ps *.dvi *.out *.log *.aux *.bbl *.blg *.pyg

.PHONY: all show clean ps pdf showps
