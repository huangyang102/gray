EXTRA_DIST = mainpage.md

all-local: html/index.html latex/refman.pdf

html/index.html:
	doxygen

latex/refman.pdf:
	if [ ! -f latex/refman.tex ]; then doxygen; fi
	cd latex; pdflatex refman; pdflatex refman; cd ..

clean-local:
	rm -rf html/ latex/
