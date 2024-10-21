SRC_DIR=src
SECTION_DIR=$(SRC_DIR)/sections
OUTDIR=build
TEXFILE=$(SRC_DIR)/main.tex
SECTFILES=$(wildcard $(SECTION_DIR)/*.tex)
PDFFILE=$(basename $(notdir $(TEXFILE))).pdf
REMISE=fj-year-plan.pdf

TEXFILES=$(TEXFILE) $(SECTFILES)

all: $(OUTDIR)/$(PDFFILE)

$(OUTDIR)/$(PDFFILE): $(TEXFILES)
	mkdir -p $(OUTDIR)
	latexmk -pdf -outdir=$(OUTDIR) $(TEXFILE)

clean:
	rm -rf $(OUTDIR)

run: all
	xdg-open $(OUTDIR)/$(PDFFILE)

remise: all
	mv $(OUTDIR)/$(PDFFILE) $(REMISE)

