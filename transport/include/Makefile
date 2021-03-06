# ====================================================================
#   "Mixed Finite Element Methods for Coupled 3D/1D Fluid Problems"
#      Course on Advanced Programming for Scientific Computing
#                     Politecnico di Milano
#                         A.Y. 2014-2015
#
#                    Copyright D. Notaro 2015
# ====================================================================
#   FILE        : Makefile
#   DESCRIPTION : makefile for library installation
#   AUTHOR      : Domenico Notaro <domenico.not@gmail.com>
#   DATE        : February 2016
# ====================================================================

include ../config.mk

CPPFLAGS=-I. -I$(GETFEM_PREFIX)/include -I$(PROBLEM_FLUID_PREFIX)/include
CXXFLAGS=-std=c++11 -Wall -fPIC
OPTFLAGS=-O3 -DNDEBUG -march=native


LIBDIR=../lib
LIBNAME=transport3d1d
LIBFILE=lib$(LIBNAME).so

LIBSRC=$(wildcard *.cpp)
LIBOBJS=$(LIBSRC:.cpp=.o)
LIBHEADERS=$(wildcard *.hpp)

.PHONY: all clean distclean library

all: library
	@echo
	@echo Library installed!

library: $(LIBOBJS)
	$(CXX) -shared -o $(LIBDIR)/$(LIBFILE) $(LIBOBJS)

%.o: %.cpp
	$(CXX) $(CPPFLAGS) $(CXXFLAGS) $(OPTFLAGS) -o $@ -c $<

clean:
	$(RM) $(LIBOBJS) *~

distclean: clean
	$(RM) $(LIBDIR)/$(LIBFILE)
