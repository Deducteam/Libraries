#put the path of your dkcheck binary
DKCHECK ?= dkcheck
#put the path of your dkdep binary
DKDEP ?= dkdep
DKOPTIONS = -nl -errors-in-snf

DKS = $(wildcard *.dk)
DKOS = $(DKS:.dk=.dko)

.PHONY:	all clean

all: $(DKOS)

%.dko: %.dk .depend
	@echo "FILE: $<"
	#time --format "TIME: %U" --output /dev/stdout $(DKCHECK) $(DKOPTIONS) -e $<
	$(DKCHECK) $(DKOPTIONS) -e $<

# standard .depend file generation
.depend: $(DKS)
	@echo "Producing .depend"
	@$(DKDEP) $^ -o $@

clean:
	@rm -f *.dko .depend tmp.dk

ifneq ($(MAKECMDGOALS), clean)
-include .depend
endif
