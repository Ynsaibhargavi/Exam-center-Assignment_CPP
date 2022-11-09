SRCDIR = src
OBJDIR = obj
INCLUDEDIR = include
BINDIR = bin
VALGRIND = tools/valgrind

INCLUDEFLAGS = -I${INCLUDEDIR}
CPPFLAGS = -ansi -c -g -Wall -DDEBUG ${INCLUDEFLAGS}

mainprogram: Candidate.o MH-CET.o UPSC.o MPSC.o NEET.o ExamCenter.o main.o
	g++ -o ${BINDIR}/mainprogram ${OBJDIR}/Candidate.o ${OBJDIR}/MH-CET.o ${OBJDIR}/UPSC.o ${OBJDIR}/MPSC.o ${OBJDIR}/NEET.o ${OBJDIR}/ExamCenter.o ${OBJDIR}/main.o

main.o:${SRCDIR}/main.cpp
	g++ -o ${OBJDIR}/main.o ${CPPFLAGS} ${SRCDIR}/main.cpp

Candidate.o: ${SRCDIR}/Candidate.cpp
	g++ -o ${OBJDIR}/Candidate.o ${CPPFLAGS} ${SRCDIR}/Candidate.cpp

MH-CET.o: ${SRCDIR}/MH-CET.cpp
	g++ -o ${OBJDIR}/MH-CET.o ${CPPFLAGS} ${SRCDIR}/MH-CET.cpp

UPSC.o: ${SRCDIR}/UPSC.cpp
	g++ -o ${OBJDIR}/UPSC.o ${CPPFLAGS} ${SRCDIR}/UPSC.cpp

MPSC.o: ${SRCDIR}/MPSC.cpp
	g++ -o ${OBJDIR}/MPSC.o ${CPPFLAGS} ${SRCDIR}/MPSC.cpp

NEET.o: ${SRCDIR}/NEET.cpp
	g++ -o ${OBJDIR}/NEET.o ${CPPFLAGS} ${SRCDIR}/NEET.cpp

ExamCenter.o : ${SRCDIR}/ExamCenter.cpp
	g++ -o ${OBJDIR}/ExamCenter.o ${CPPFLAGS} ${SRCDIR}/ExamCenter.cpp

valgrind :mainprogram
	valgrind --leak-check=full --show-reachable=yes ${BINDIR}/mainprogram 2> ${VALGRIND}/valgrind.txt
	
clean :
	echo "cleaning up .o and exes"
	rm ${BINDIR}/mainprogram ${OBJDIR}/main.o ${OBJDIR}/Candidate.o ${OBJDIR}/MH-CET.o ${OBJDIR}/UPSC.o ${OBJDIR}/MPSC.o ${OBJDIR}/NEET.o ${OBJDIR}/ExamCenter.o ${VALGRIND}/valgrind.txt
