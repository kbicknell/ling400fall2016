hwbase=hw0 hw1 hw2 hw3 hw4
hwhtml=$(addsuffix .html, $(hwbase))
all : $(hwhtml)

.PHONY : all clean

%.html : %.Rmd
	Rscript -e "require(rmarkdown); render('$<')"

hw1.html : hw1.Rmd fsa.svg
	Rscript -e "require(rmarkdown); render('$<')"

%.svg : %.pdf
	pdf2svg $^ $@
%.pdf : %.tex
	pdflatex $^

clean :
	rm -f $(hwhtml)
	rm -f fsa.pdf fsa.svg fsa.log fsa.aux
