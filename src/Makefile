ldfs=datatool-english.ldf \
datatool-english-ascii.ldf \
datatool-english-latin1.ldf \
datatool-english-utf8.ldf \
datatool-en-CA.ldf \
datatool-en-ZA.ldf \
databib-english.ldf \
person-english.ldf \
datatool-anglosaxon.ldf \
datatool-ang-Latn.ldf \
datatool-ang-Latn-utf8.ldf \
datatool-ang-Runr.ldf \
datatool-ang-Runr-utf8.ldf 

all	: test-english.pdf test-datatool.pdf \
	test-datagidx.pdf test-glossarynoidx.pdf \
	test-anglosaxon.pdf test-runes.pdf

test-english.pdf	: test-english.tex $(ldfs)
	pdflatex test-english.tex

test-datatool.pdf	: test-datatool.tex $(ldfs)
	pdflatex test-datatool.tex

test-anglosaxon.pdf	: test-anglosaxon.tex $(ldfs)
	lualatex test-anglosaxon.tex

test-runes.pdf	: test-runes.tex $(ldfs)
	lualatex test-runes.tex

clean	:
	\rm -f *.out *.pdf *.log *.aux
