THISDIR := phy2403-quantum-field-theory
THISBOOK := phy2403

BIBLIOGRAPHY_PATH := classicthesis_mine
HAVE_OWN_CONTENTS := 1
#HAVE_OWN_TITLEPAGE := 1
HAVE_CUSTOM_DEDICATION := 1
MY_CLASSICTHESIS_FRONTBACK_FILES += ../latex/classicthesis_mine/FrontBackmatter/Index.tex
MY_CLASSICTHESIS_FRONTBACK_FILES += ../latex/classicthesis_mine/FrontBackmatter/ContentsAndFigures.tex
BOOKTEMPLATE := ../latex/classicthesis_mine/ClassicThesis2.tex

# comment this out for online pdf version (uncomment for KDP)
#PRINT_VERSION := 1
ifndef PRINT_VERSION
PARAMS += --no-print
endif
ifdef PRINT_VERSION
DISTEXTRA := kdp
endif

include make.revision
include ../latex/make.bookvars

#ONCEFLAGS := -justonce

SOURCE_DIRS += appendix
FIGURES := ../figures/$(THISBOOK)
SOURCE_DIRS += $(FIGURES)

#GENERATED_SOURCES += matlab.tex
GENERATED_SOURCES += mathematica.tex
GENERATED_SOURCES += backmatter.tex
#GENERATED_SOURCES += julia.tex

SOURCES += noetherCurrentScalarField.tex
SOURCES += scalarFieldCreationOpCommutator.tex
SOURCES += scalarFieldHamiltonian.tex
SOURCES += qftProblemSet1.tex
#SOURCES += qftProblemSet2.tex

EPS_FILES := $(wildcard $(FIGURES)/*.eps)
PDFS_FROM_EPS := $(subst eps,pdf,$(EPS_FILES))

THISBOOK_DEPS += $(PDFS_FROM_EPS)
#THISBOOK_DEPS += macros_mathematica.sty

#CLEAN_TARGETS += ps5mathematica.tex ps9mathematica.tex
CLEAN_TARGETS += *.sp
#CLEAN_TARGETS += FrontBackmatter/*.sp

#SPELLCHECK := $(patsubst %.tex,%.sp,$(wildcard *.tex))
DO_SPELL_CHECK := $(shell cat spellcheckem.txt)
SPELLCHECK := $(patsubst %.tex,%.sp,$(DO_SPELL_CHECK))

include ../latex/make.rules

#all :: l1
#all :: l2
#all :: l3
#all :: l4
#all :: l5
#all :: l6
#all :: l7
#all :: l8
#all :: l9
#all :: l10
#all :: l11
#all :: l12
#all :: l13
#all :: l14
#all :: l15
#all :: l15b
#all :: l16
all :: l17
#all :: l18
#all :: l19
#all :: l20
#all :: l21
#all :: l21b
#all :: l22
#all :: l23
#all :: p1
#all :: p2
#all :: p3
#all :: p4
all :: p5

$(THISBOOK).pdf :: $(shell cat spellcheckem.txt)

#l1: qftLecture1.pdf
#l2: qftLecture2.pdf
#l3: qftLecture3.pdf
#l4: qftLecture4.pdf
#l5: qftLecture5.pdf
#l6: qftLecture6.pdf
#l7: qftLecture7.pdf
#l8: qftLecture8.pdf
#l9: qftLecture9.pdf
#l10: qftLecture10.pdf
#l11: qftLecture11.pdf
#l12: qftLecture12.pdf
#l13: qftLecture13.pdf
#l14: qftLecture14.pdf
#l15: qftLecture15.pdf
#l15b: qftLecture15b.pdf
#l16: qftLecture16.pdf
l17: q17.pdf
q17.pdf : qftLecture17.tex
q17.pdf : qftLecture18.tex
#l18: qftLecture18.pdf
#l19: qftLecture19.pdf
#l20: qftLecture20.pdf
#l21: qftLecture21.pdf
#l21b: qftLecture21b.pdf
#l22: qftLecture22.pdf
#l23: qftLecture23.pdf
#p1: ProblemSet1.pdf
#p2: ProblemSet2.pdf
#p3: ProblemSet3.pdf
p4: ProblemSet4.pdf
p5: ProblemSet5.pdf
#q: QandA.pdf
#l: lukenotetypos.pdf
#dr: diracuv.pdf
#ss: spinorSolutions.pdf

qftLukeProblemSet1.pdf : qftLukeProblemSet1Problem1.tex
qftLukeProblemSet1.pdf : qftLukeProblemSet1Problem2.tex
qftLukeProblemSet1.pdf : qftLukeProblemSet1Problem3.tex
qftLukeProblemSet1.pdf : qftLukeProblemSet1Problem4.tex
qftLukeProblemSet1.pdf : qftLukeProblemSet1Problem5.tex
qftLukeProblemSet1.pdf : qftLukeProblemSet1Problem6.tex

ProblemSet1.pdf : ProblemSet1Problem1.tex
ProblemSet1.pdf : ProblemSet1Problem2.tex
ProblemSet1.pdf : ProblemSet1Problem3.tex
ProblemSet1.pdf : ProblemSet1Problem4.tex
ProblemSet1.pdf : ProblemSet1Problem5.tex

ProblemSet3.pdf : ProblemSet3Problem1.tex
ProblemSet3.pdf : ProblemSet3Problem2.tex
ProblemSet3.pdf : ProblemSet3Problem3.tex
ProblemSet3.pdf : ProblemSet3Problem4.tex

ProblemSet4.pdf : ProblemSet4Problem1.tex
ProblemSet4.pdf : ProblemSet4Problem2.tex
ProblemSet4.pdf : ProblemSet4Problem3.tex
ProblemSet4.pdf : ProblemSet4Problem4.tex

ProblemSet5.pdf : ProblemSet5Problem1.tex
ProblemSet5.pdf : ProblemSet5Problem2.tex
ProblemSet5.pdf : ProblemSet5Problem3.tex

.PHONY: spellcheck
spellcheck: $(SPELLCHECK)

%.sp : %.tex
	spellcheck $^
	touch $@

mmacells/mmacells.sty:
	git clone https://github.com/jkuczm/mmacells

bib:
	rm -f Bibliography.bib myrefs.bib
	make Bibliography.bib myrefs.bib

mmacells.sty: mmacells/mmacells.sty
	cp $^ $@

#julia.tex : ../julia/METADATA
mathematica.tex : ../mathematica/METADATA
#matlab.tex : ../matlab/METADATA

dropbox:
	cp $(THISBOOK).pdf ~/Dropbox/$(THISDIR)/$(THISBOOK).$(VER).pdf
	git log --decorate > ~/Dropbox/$(THISDIR)/Changelog.txt

%.sp : %.tex
	spellcheck $^
	touch $@

.PHONY: copy
copy : $(HOME)/Dropbox/$(THISDIR)/$(THISBOOK).pdf

$(HOME)/Dropbox/$(THISDIR)/$(THISBOOK).pdf : $(THISBOOK).pdf
	cp $^ $@

backmatter.tex: ../latex/classicthesis_mine/backmatter2.tex
	rm -f $@
	ln -s ../latex/classicthesis_mine/backmatter2.tex backmatter.tex
