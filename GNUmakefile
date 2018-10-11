THISDIR := phy2403-quantum-field-theory
THISBOOK := phy2403

export BOOKSUBVER := 1
export BOOKMAJVER := 0
# This isn't a good way to version.  It depends on the local git reflog history count.
export REVCOUNTSTART := 1

include ../latex/make.bookvars

#ONCEFLAGS := -justonce

SOURCE_DIRS += appendix
FIGURES := ../figures/$(THISBOOK)
SOURCE_DIRS += $(FIGURES)

# also toggle redacted classicthesis-config.tex
# FIXME: changing this flag should be a dependency of matlab.tex 
#REDACTED := -redacted

#GENERATED_SOURCES += matlab.tex 
#GENERATED_SOURCES += mathematica.tex 
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
all :: l8
#all :: l9
all :: l10
#all :: p1
#all :: p2

$(THISBOOK).pdf :: $(shell cat spellcheckem.txt)

#l1: qftLecture1.pdf
#l2: qftLecture2.pdf
#l3: qftLecture3.pdf
#l4: qftLecture4.pdf
#l5: qftLecture5.pdf
#l6: qftLecture6.pdf
#l7: qftLecture7.pdf
l8: qftLecture8.pdf
#l9: qftLecture9.pdf
l10: qftLecture10.pdf
#p1: ProblemSet1.pdf
p2: ProblemSet2.pdf

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

ProblemSet2.pdf : ProblemSet2Problem1.tex
ProblemSet2.pdf : ProblemSet2Problem2.tex
ProblemSet2.pdf : ProblemSet2Problem3.tex
ProblemSet2.pdf : ProblemSet2Problem4.tex

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
#mathematica.tex : ../mathematica/METADATA
#matlab.tex : ../matlab/METADATA
