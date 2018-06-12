TEX_FILE_BASENAME=skanda
TEX_FILE=$(TEX_FILE_BASENAME).tex

.PHONY: all pdf html epub

all: pdf html epub

pdf:
	xelatex $(TEX_FILE); cp *.pdf ../pdf

html:
	pandoc --from latex --pdf-engine=xelatex --to html5 $(TEX_FILE) -o $(TEX_FILE_BASENAME).html --default-image-extension jpg

#	make4ht -ux $(TEX_FILE)

epub:
	ebook-convert $(TEX_FILE).html $(TEX_FILE).epub --language en --no-default-epub-cover

html_latexml:
	latexml --dest=$(TEX_FILE).xml $(TEX_FILE).tex ;\
	latexmlpost -dest=$(TEX_FILE).html $(TEX_FILE).xml ;\
