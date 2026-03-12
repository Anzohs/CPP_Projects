LATEX=pdflatex
LATEXFLAGS=-interaction=nonstopmode -halt-on-error -file-line-error
OUT=out

SUBJECTS=webserv++ minidb++ tinycc++ irc-lite++ chesslite++

all: $(OUT) $(OUT)/back.pdf $(SUBJECTS:%=$(OUT)/%.pdf)

$(OUT):
	mkdir -p $(OUT)

$(OUT)/back.pdf: back.tex 42subject.sty
	$(LATEX) $(LATEXFLAGS) -output-directory=$(OUT) back.tex
	$(LATEX) $(LATEXFLAGS) -output-directory=$(OUT) back.tex

$(OUT)/%.pdf: %.tex 42subject.sty $(OUT)/back.pdf
	$(LATEX) $(LATEXFLAGS) -output-directory=$(OUT) "$<"
	$(LATEX) $(LATEXFLAGS) -output-directory=$(OUT) "$<"

clean:
	rm -rf $(OUT)

.PHONY: all clean
