# ====================================================================
#   "Mixed Finite Element Methods for Coupled 3D/1D Fluid Problems"
#      Course on Advanced Programming for Scientific Computing
#                     Politecnico di Milano
#                         A.Y. 2014-2015
#
#                    Copyright D. Notaro 2015
# ====================================================================
#   FILE        : Makefile
#   DESCRIPTION : makefile for test simulations
#   AUTHOR      : Domenico Notaro <domenico.not@gmail.com>
#   DATE        : November 2015
# ====================================================================

.PHONY: all doc clean distclean library

all: library
	$(MAKE) -C src/1_singlebranch_transp 
	$(MAKE) -C src/2_Ybifurcation_transp 
	$(MAKE) -C src/3_network_transp 

library: 
	$(MAKE) -C include

doc:
	install -d doc
	doxygen Doxyfile
	
pdf: doc
	$(MAKE) -C doc/latex pdf

clean:
	$(RM) -r *~ *.log
	$(MAKE) -C include clean
	$(MAKE) -C src/1_singlebranch_transp clean
	$(MAKE) -C src/2_Ybifurcation_transp clean
	$(MAKE) -C src/3_network_transp clean
	
distclean: clean
	$(RM) -r doc/*
	$(MAKE) -C include distclean
	$(MAKE) -C src/1_singlebranch_transp distclean
	$(MAKE) -C src/2_Ybifurcation_transp distclean
	$(MAKE) -C src/3_network_transp distclean
