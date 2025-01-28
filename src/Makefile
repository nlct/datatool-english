ldfs=datatool-english.ldf \
datatool-english-ascii.ldf \
datatool-english-latin1.ldf \
datatool-english-utf8.ldf \
datatool-en-CA.ldf \
datatool-en-ZA.ldf \
databib-english.ldf \
person-english.ldf 

all	: test-english.pdf

test-english.pdf	: test-english.tex $(ldfs)
	pdflatex test-english.tex

clean	:
	\rm -f *.out *.pdf *.log *.aux
