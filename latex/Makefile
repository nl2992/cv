# Build every CV version into pdf/.  Requires tectonic (brew install tectonic)
# or a TeX distribution with xelatex:  make ENGINE=xelatex
ENGINE ?= tectonic
SOURCES := $(filter-out cv.sty,$(wildcard *.tex))
PDFS    := $(patsubst %.tex,pdf/%.pdf,$(SOURCES))

all: $(PDFS)
	@cp $(PDFS) ..
	@echo "copied $(words $(PDFS)) PDFs to repo root"

pdf/%.pdf: %.tex cv.sty | pdf
ifeq ($(ENGINE),tectonic)
	tectonic -X compile --outdir pdf $<
else
	$(ENGINE) -interaction=nonstopmode -halt-on-error -output-directory=pdf $< >/dev/null
	$(ENGINE) -interaction=nonstopmode -halt-on-error -output-directory=pdf $< >/dev/null
	rm -f pdf/$*.aux pdf/$*.log pdf/$*.out
endif

pdf:
	mkdir -p pdf

clean:
	rm -rf pdf

.PHONY: all clean
