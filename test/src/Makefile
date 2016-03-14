CXX = g++
CXXFLAGS = -g -L/opt/gtest/lib -lgtest -lpthread
INCS = -I./ -I../../src -I/opt/gtest/include
OBJS = ../../src/Addition.o Addition_Test.o ../../src/Multiply.o Multiply_Test.o

ifeq ($(OS),Windows_NT)
OBJS += gtest-all.o
GTEST_DIR = C:/gtest-1.7.0/
endif





testAll: $(OBJS)
	$(CXX) $(CXXFLAGS) $(INCS) -o testAll  Main_TestAll.cpp $(OBJS)

.cpp.o:
	$(CXX) $(CXXFLAGS) -c $< -o $@ $(INCS)
ifeq ($(OS),Windows_NT)
gtest-all.o:
	g++ -o $@ -c -I$(GTEST_DIR) -I$(GTEST_DIR)include $(GTEST_DIR)src/gtest-all.cc
gtest_main.o:
	g++ -o $@ -c -I$(GTEST_DIR) -I$(GTEST_DIR)include $(GTEST_DIR)src/gtest_main.cc
endif
clean:
	rm testAll *.o testAll.xml