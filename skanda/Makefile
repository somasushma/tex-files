TEX_FILE_BASENAME=skanda
TEX_FILE=$(TEX_FILE_BASENAME).tex

.PHONY: all pdf html epub

all: pdf html epub

pdf:
	xelatex $(TEX_FILE); cp *.pdf ../pdf

html:
	pandoc --from latex --pdf-engine=xelatex --to html5 $(TEX_FILE) -o $(TEX_FILE_BASENAME).html --default-image-extension jpg --extract-media=html_images

epub: html
	ebook-convert $(TEX_FILE_BASENAME).html $(TEX_FILE_BASENAME).epub --language en --no-default-epub-cover; cp *.epub ../epub

html_latexml:
	latexml --dest=$(TEX_FILE).xml $(TEX_FILE).tex ;\
	latexmlpost -dest=$(TEX_FILE).html $(TEX_FILE).xml ;\
