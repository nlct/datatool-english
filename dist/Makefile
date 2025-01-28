datatool-english.zip	: datatool-english.dtx datatool-english.ins \
	datatool-english.pdf README.md DEPENDS.txt
	mkdir -p datatool-english
	cp datatool-english.{dtx,ins,pdf} README.md DEPENDS.txt datatool-english
	zip --exclude="*.swp" -r datatool-english.zip datatool-english

datatool-english.pdf	: datatool-english.dtx datatool-english.ldf
	pdflatex datatool-english.dtx
	makeindex -s gind.ist datatool-english.idx
	makeindex -s gglo.ist -o datatool-english.gls datatool-english.glo
	pdflatex datatool-english.dtx
	makeindex -s gind.ist datatool-english.idx
	makeindex -s gglo.ist -o datatool-english.gls datatool-english.glo
	pdflatex datatool-english.dtx
	pdflatex datatool-english.dtx

datatool-english.ldf	: datatool-english.dtx datatool-english.ins
	latex datatool-english.ins

clean	:
	\rm -f *.ldf *.out *.log *.pdf *.dtx *.ins README.md
