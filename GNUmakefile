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
all :: l2
all :: l3
all :: p1
#all :: p2

$(THISBOOK).pdf :: $(shell cat spellcheckem.txt)

#l1: qftLecture1.pdf
l2: qftLecture2.pdf
l3: qftLecture3.pdf
p1: ProblemSet1.pdf

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

.PHONY: spellcheck
spellcheck: $(SPELLCHECK)

%.sp : %.tex
	spellcheck $^
	touch $@

#julia.tex : ../julia/METADATA
#mathematica.tex : ../mathematica/METADATA
#matlab.tex : ../matlab/METADATA
