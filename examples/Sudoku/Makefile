
DKCHECK?=dkcheck
DKFLAGS?=-e -nl

all : empty easy medium hardest

empty  : solve_empty.dko
easy   : solve_easy.dko
medium : solve_medium.dko
hardest: solve_hardest.dko

sudoku.dko : sudoku.dk
	$(DKCHECK) $(DKFLAGS) sudoku.dk

%.dko: %.dk sudoku.dko
	$(DKCHECK) $<

clean:
	rm -rf *.dko
