ldfs=datatool-english.ldf \
datatool-english-ascii.ldf \
datatool-english-latin1.ldf \
datatool-english-utf8.ldf \
datatool-en-CA.ldf \
datatool-en-ZA.ldf \
databib-english.ldf \
person-english.ldf 

../dist/datatool-english.dtx	: datatool-english.tex version.txt $(ldfs)
	makedtx -author "Nicola Talbot" \
	-src "(datatool-english*.ldf)\Z=>\1" \
	-src "(datatool-en-*.ldf)\Z=>\1" \
	-src "(databib-english.ldf)\Z=>\1" \
	-src "(person-english.ldf)\Z=>\1" \
	-doc datatool-english.tex datatool-english
	cp2dist -f version.txt datatool-english.{dtx,ins} ../dist
	rm -f datatool-english.{dtx,ins}

clean	:
	\rm -f datatool-english.{dtx,ins}
