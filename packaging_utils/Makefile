web : build_docs build_examples build_version copy_module

examples : build_examples

docs : build_docs

#ROOT=/Users/todd
HTML=/usr/local/public_html/toddot/html/projects/GD-SVG
BIOP=/Users/todd/projects/bioperl-live/examples/biographics
EXAMPLES=${HTML}/examples

build_docs:
	pod2html --infile ../SVG.pm --outfile ${HTML}/GD-SVG.html
	rm -rf pod2htm*
	cp ../Changes ${HTML}/change_log.txt

build_examples:
	../examples/generate_test_image.pl GD > ${EXAMPLES}/gd-svg-test.png
	../examples/generate_test_image.pl GD::SVG > ${EXAMPLES}/gd-svg-test.svg
	${BIOP}/dynamic_glyphs.pl GD > ${EXAMPLES}/biographics-dynamic.png
	${BIOP}/dynamic_glyphs.pl GD::SVG > ${EXAMPLES}/biographics-dynamic.svg
	${BIOP}/lots_of_glyphs.pl GD > ${EXAMPLES}/biographics-lots.png
	${BIOP}/lots_of_glyphs.pl GD::SVG > ${EXAMPLES}/biographics-lots.svg
	${BIOP}/all_glyphs.pl GD > ${EXAMPLES}/biographics-all_glyphs.png
	${BIOP}/all_glyphs.pl GD::SVG > ${EXAMPLES}/biographics-all_glyphs.svg
	${BIOP}/all_glyphs.pl GD 275 325 > ${EXAMPLES}/biographics-all_glyphs-hi_mag.png
	${BIOP}/all_glyphs.pl GD::SVG 275 325 > ${EXAMPLES}/biographics-all_glyphs-hi_mag.svg

build_version:
	./parse_version
	cp GD-SVG.version ${HTML}/.

copy_module:
	cp ../GD-SVG*.tar.gz ${HTML}/releases/.
