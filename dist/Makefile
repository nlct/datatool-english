ldfs=../src/datatool-english.ldf \
../src/datatool-english-ascii.ldf \
../src/datatool-english-latin1.ldf \
../src/datatool-english-utf8.ldf \
../src/datatool-en-CA.ldf \
../src/datatool-en-ZA.ldf \
../src/databib-english.ldf \
../src/person-english.ldf \
../src/datatool-anglosaxon.ldf \
../src/datatool-ang-Latn.ldf \
../src/datatool-ang-Latn-utf8.ldf \
../src/datatool-ang-Runr.ldf \
../src/datatool-ang-Runr-utf8.ldf 

datatool-english.zip	: datatool-english.dtx datatool-english.ins \
	datatool-english.pdf README.md DEPENDS.txt
	mkdir -p datatool-english
	cp datatool-english.{dtx,ins,pdf} README.md DEPENDS.txt datatool-english
	zip --exclude="*.swp" -r datatool-english.zip datatool-english

datatool-english.pdf	: datatool-english.dtx datatool-english.ldf
	lualatex datatool-english.dtx
	makeindex -s gind.ist datatool-english.idx
	makeindex -s gglo.ist -o datatool-english.gls datatool-english.glo
	lualatex datatool-english.dtx
	makeindex -s gind.ist datatool-english.idx
	makeindex -s gglo.ist -o datatool-english.gls datatool-english.glo
	lualatex datatool-english.dtx
	lualatex datatool-english.dtx

datatool-english.ldf	: datatool-english.dtx datatool-english.ins
	latex datatool-english.ins

datatool-english.dtx	: ../src/datatool-english.tex ../src/version.txt $(ldfs)
	cd ../src; makedtx -author "Nicola Talbot" \
	-src "(datatool-english\.ldf)\Z=>\1" \
	-src "(datatool-english-.*\.ldf)\Z=>\1" \
	-src "(datatool-en-.*\.ldf)\Z=>\1" \
	-src "(databib-english\.ldf)\Z=>\1" \
	-src "(person-english\.ldf)\Z=>\1" \
	-src "(datatool-anglosaxon\.ldf)\Z=>\1" \
	-src "(datatool-ang-Latn\.ldf)\Z=>\1" \
	-src "(datatool-ang-Latn-.*\.ldf)\Z=>\1" \
	-src "(datatool-ang-Runr\.ldf)\Z=>\1" \
	-src "(datatool-ang-Runr-.*\.ldf)\Z=>\1" \
	-doc datatool-english.tex datatool-english
	cp2dist -f ../src/version.txt ../src/datatool-english.{dtx,ins} .
	rm -f ../src/datatool-english.{dtx,ins}

README.md	: ../src/README.md
	cp2dist -f ../src/version.txt ../src/README.md .

clean	:
	\rm -f *.ldf *.out *.log *.aux *.pdf *.dtx *.ins *.ind *.idx *.ilg *.glo *.gls *.glg *.hd README.md
	\rm -f datatool-english.zip
