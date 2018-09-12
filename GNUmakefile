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

SPELLCHECK := $(patsubst %.tex,%.sp,$(wildcard *.tex))

include ../latex/make.rules

all :: l1
all :: l2
#all :: p2

l1: qftLecture1.pdf
l2: qftLecture2.pdf

qftProblemSet1.pdf : qftProblemSet1Problem1.tex
qftProblemSet1.pdf : qftProblemSet1Problem2.tex
qftProblemSet1.pdf : qftProblemSet1Problem3.tex
qftProblemSet1.pdf : qftProblemSet1Problem4.tex
qftProblemSet1.pdf : qftProblemSet1Problem5.tex
qftProblemSet1.pdf : qftProblemSet1Problem6.tex

#qftProblemSet2.pdf : qftProblemSet2Problem1.tex
#qftProblemSet2.pdf : qftProblemSet2Problem2.tex
#qftProblemSet2.pdf : qftProblemSet2Problem3.tex
#qftProblemSet2.pdf : qftProblemSet2Problem4.tex
#qftProblemSet2.pdf : qftProblemSet2Problem5.tex

.PHONY: spellcheck
spellcheck: $(SPELLCHECK)

%.sp : %.tex
	spellcheck $^
	touch $@

#julia.tex : ../julia/METADATA
#mathematica.tex : ../mathematica/METADATA
#matlab.tex : ../matlab/METADATA
