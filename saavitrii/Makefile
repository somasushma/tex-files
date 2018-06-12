TEX_FILE=Savitri.tex

.PHONY: all pdf html epub

all: pdf html epub

pdf:
	xelatex $(TEX_FILE); cp *.pdf ../pdf

html:
	pandoc --from latex --to html5 $(TEX_FILE) -o $(TEX_FILE).html

epub:
	ebook-convert $(TEX_FILE).html $(TEX_FILE).epub --language en --no-default-epub-cover

html_latexml:
	latexml --dest=$(TEX_FILE).xml $(TEX_FILE).tex ;\
	latexmlpost -dest=$(TEX_FILE).html $(TEX_FILE).xml ;\
