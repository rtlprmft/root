# Copyright (C) 1995-2019, Rene Brun and Fons Rademakers.
# All rights reserved.
#
# For the licensing terms see $ROOTSYS/LICENSE.
# For the list of contributors see $ROOTSYS/README/CREDITS.

############################################################################
# CMakeLists.txt file for PyMVA  package
############################################################################
#Autor: Omar  Zapata, Lorenzo Moneta, Sergei Glayzer 22/08/2015
#website:http://oproject.org

include_directories(SYSTEM ${PYTHON_INCLUDE_DIRS_Development_Main} ${NUMPY_INCLUDE_DIRS})

ROOT_STANDARD_LIBRARY_PACKAGE(PyMVA
  HEADERS
    TMVA/MethodPyAdaBoost.h
    TMVA/MethodPyGTB.h
    TMVA/MethodPyKeras.h
    TMVA/MethodPyRandomForest.h
    TMVA/PyMethodBase.h
  SOURCES
    src/MethodPyAdaBoost.cxx
    src/MethodPyGTB.cxx
    src/MethodPyKeras.cxx
    src/MethodPyRandomForest.cxx
    src/PyMethodBase.cxx
  LIBRARIES
  ${PYTHON_LIBRARIES_Development_Main}
  DEPENDENCIES
    Core
    Matrix
    Thread
    RIO
    TMVA
)

ROOT_ADD_TEST_SUBDIRECTORY(test)
