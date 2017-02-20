CHAPTER NINE
Studies of Computer Techniques and Procedures
The following eight studies are concerned with early
steps along the course from present digital-computer system to future procognitive systems. Let us consider the studies in the order of their locations along that course.
The first ones were intended merely to make it convenient to carry out some of the functions that are required in research on library and procognitive problems or in the efficient use of large collections of documents. The last
ones in the sequence were intended to explore functions
that we think will actually be involved in future procogni-
tive systems.
157

explorations in the use of computers
An "Executive" Program to Facilitate the Use
OF the PDP-1 Computer
One of the first needs of the study was a computer program to facilitate the programming and use of the laboratory's digital computer. The computer is a small but excellent machine, Digital Equipment Corporation PDP-1, specialized to facilitate interaction with users who work "on line." The PDP-1 has an oscilloscope display with
light pen, several electric typewriters, a set of programmable relays, an analogue-to-digital converter, and an as-
sortment of switches and buttons. Its primary memory is
small (8196 eighteen-bit words), but it is capable of transferring information rapidly between the primary
memory and a secondary drum memory that holds about
90,000 eighteen-bit words. Associated with the computer are two magnetic-tape units. With the computer, it is possible to implement, in a preliminary and schematic way, several of the functions that were described in Part I
as functions desirable in a procognitive system.
One encounters two main difficulties in trying to do, with the PDP-1 computer, research oriented toward a
future period in which information-processing machines will have more advanced capabilities. First, although the
machine is reasonably fast (5-microsecond memory
cycle), and although its secondary and tertiary memories make it possible to work with significantly large bodies of information, the machine is not capable of performing deep and complicated operations on really large bodies of text with the speed that would be desired in an opera-
tional system. The result is that it may take 30 seconds
or a minute to get something that one would like to have
158

COMPUTER TECHNIQUES AND PROCEDURES

almost instantly, that the display flickers on the oscillo-

scope screen, and so forth. Second, there is not available,

at present, on any machine, either a programming lan-

guage or a man-machine interaction (user-oriented) lan-

guage that makes it easy to do, or possible to do rapidly,

many of the things envisioned in the discussion of procog-

nitive systems in Part I of this report. Our approach, dur-

ing the study, was simply to put up with, and make allow-

ances for, the shortcomings of the hardware system. It

was easy to do that in informal experiments conducted

by members of the research group; it was not realistic,

however, to hope that all the observers of demonstrations

would make the necessary allowances, and the shortcom-

ings of the equipment (compared to what we expect to

have in two decades) effectively precluded formal ex-

perimentation. Nevertheless, the equipment situation was

at least tolerable, in terms of absolute assessment, and it

seemed superb when we compared our man-computer

interaction situation with any but two or three of all the

others with which we were acquainted.
--The unavailability of highly developed languages

and, of course, the interpreter and compiler programs
--that would be required to make them useful was, how-

ever, a seriously inhibiting factor. During the period of

our study, two good programming-language systems came

into being: DECAL, which is a quite elegant and power-

ALGOLful language and compiler of the

type, suitable

for a small computer, and MACRO, which is an ingen-

ious language and assembler system that incorporates

DECALseveral of the features that

lacks and lacks sev-

DECALeral of the features that

incorporates. However,

MACROneither DECAL nor

was designed for on-line

159

EXPLORATIONS IN THE USE OF COMPUTERS
programming, and neither was designed particularly to handle the problems that seem likely to present themselves
to users of procognitive systems.
Those considerations led to the effort, which was never quite completed, to develop a composite programmeroriented and user-oriented system to facilitate our research in man-machine interaction. The system is called "Exec," which stands, of course, for "executive program"
and thus expresses something about the mode of opera-
tion: statements of the input language, coming into the computer, are examined by the executive program, and, depending upon whether or not they fall into the class requiring interpretation, are either interpreted and executed
with the aid of a set of subroutines associated with the
executive program or simply executed as machine instruc-
tions.
Exec was written originally in the symbolic language
called "FRAP" and had, as its main function, simplifica-
tion of the preparation of programs and subroutines to be
translated and assembled by FRAP. When DECAL be-
came available. Exec was rewritten in DECAL, and
slight modifications were made to facihtate the use of Exec in the preparation of programs and subroutines to
--be translated and compiled by DECAL. The original in-
tention to develop Exec to the point at which it could
--operate as an on-Hne language as well as an adjunct to
a programming language was not accomplished. One of the main themes in the work on Exec was to
simplify and regularize the "calling" and "returning" of subroutines. In most computer-programming systems, and especially in the computer-programming systems that will be required in the implementation of plans of the kind described in Part I, a computer program is a complex
160

COMPUTER TECHNIQUES AND PROCEDURES
arrangement of parts. The highest echelon of the structure does little more than represent the chapter headings
--of the general plan. The actual work the detailed --processing of data is handled by subprograms or "sub-
routines" that break the task down into successively sim-
pler subpackages at successively lower levels of detail until, finally, there is nothing left for the lowest-echelon subprograms to do but to perform simple, explicitly defined operations upon the few codes or numbers that are suppHed to them. In this process of successive delegation of responsibility, the transactions that appear repeatedly are the "calling" of a lower-echelon subroutine by a higher-echelon subroutine and the "returning" of control from the lower-echelon subroutine to the higher-echelon subroutine. Calling usually includes transmission of instructions, and also the designation of the arguments upon which the lower-echelon subroutine must operate, from
the calling subroutine to the called subroutine. The transmission of information down the line we shall call "briefing." Transmission of results up the fine we shall call
"debriefing."
In the conventional way of handling calling and re-
turning, a subroutine eventually returns control to the
subroutine that called it, but it may first call one or more
lower-echelon subroutines.
Fortunately or unfortunately, depending upon one's point of view, there are many different ways in which subroutines can be called and briefed and in which they can return control and do their debriefing. As indicated, one of the main purposes of Exec is to simpUfy and regularize this whole process.
In order to simplify the process of calling and returning, Exec is interposed between the calling subroutine and
161

EXPLORATIONS IN THE USE OF COMPUTERS
the called subroutine at the time of calling and between
the called (and now returning) subroutine and the calling (and now receiving) subroutine at the time of re-
turning. With each subroutine is associated a compact code, that provides Exec with a description of the needs of the subroutine. Exec can therefore handle in a systematic, centralized manner several of the functions that would otherwise have to be handled by each subroutine. In taking a burden off the routines. Exec takes a burden off the programmers who prepare them.
The arrangements in Exec for calling and returning are set up in such a way that the chain of subroutine calls can be recursive. That is to say, it is possible for sub-
routine A to call subroutine A, or for subroutine A to call a subroutine B which, directly or through one of its minions, called subroutine A . To permit recursive opera-
--tion, one must handle "temporary storage" storage of --the scratch-pad jottings made by each subroutine during
its operation in such a way that results written by B,
for example, do not destroy results that A calculated before calling B and will need to use after B returns con-
trol.
--The functions just described have been implemented
in a few programming systems notably in the systems called IPL and LISP. In IPL and LISP, however, one either works wholly within the system or does not use the system at all. Exec extends the basic programming lan-
guage (DECAL) and provides the new capabilities and conveniences within the structure of DECAL.
In implementing the handling of subroutines, we made
Ause of the technique of the "pushdown list." pushdown
list (or "stack") is an arrangement for storing information that resembles the spring-supported tray on which
162

COMPUTER TECHNIQUES AND PROCEDURES
plates are stored in restaurants. If one puts a plate (computer word) onto the top of the stack, it pushes all the others down, and if one then takes the plate (word) off the top, the others pop up again. Exec, itself, employs one pushdown list. Another pushdown list is available to
the programmer or user through simple commands. He has only to give the name of the entity to be stored into
the pushdown list or returned from it and to say whether he wants to push it down or pop it up. In the process of handling a call to a subroutine or a return from a subroutine. Exec examines the subroutine's heading code, determines whether or not, and how, to fulfill each of a number of functions, and then carries out those required. These functions include protecting contents of certain
special registers of the processor against destruction during the running of the subroutine, finding the arguments
needed by the subroutine and displaying them for its use, accepting the results obtained by the subroutine and communicating them to the calling routine, and protecting the contents of various temporary storage registers and "flag" registers against modification by the called subroutine. Exec protects information by putting it into the pushdown
list.
A second general purpose of Exec is to provide the
advantages of generality and the advantages of specificity, both at the same time and within the same system. If a computer program is written in such a way as to make it
--useful in a particular situation for example, to make
it operate on words and not sentences, and on the con-
--tents of Table 3 instead of the contents of Table 4
then a new program must be written every time the spe-
cifics of the problem change. On the other hand, if the
program is written so that for example, it alphabetizes or
163

EXPLORATIONS IN THE USE OF COMPUTERS
orders any kind of strings of alphanumeric text in any file
or table, then, when the programmer starts to use it on the words listed in Table 3, he has to communicate to it, or have the routine that calls it communicate to it, that it should operate on words and on Table 3, and that it
should alphabetize according to a specified alphabet.
In Exec, an effort is made to accommodate very general subroutines and to make it maximally convenient to communicate to them the information required to prepare them for specific applications. This is done by setting up and maintaining a description of the prevailing context
of operation. In the terms of the example, his description
may contain a specification that the currently prevailing
string class is the class of "words." It contains the specification that the x, in any subroutine prepared to operate
upon "Table x," should be interpreted as 3. The subroutine, therefore, automatically performs on Table 3 the operation intended by the programmer, despite the fact that the programmer was thinking in terms of abstractions and not in terms of the particular present task. (Exec makes it possible to write subroutines in terms of
Atable variables jc, y, and z simultaneously. sequence of
sentences can, for example, be taken out of Table x, and the odd-numbered ones can be stored in Table y and the even-numbered ones in Table z. The values of x, y, and z can be set later to 17, 4, and 11, respectively.)
With arrangements of the kind just suggested, Exec makes it possible to use a subroutine that contains the expression, "next string," for example, to operate on the next character, or the next word, or the next sentence, or
the next paragraph, or the next section, or the next chapter, and so forth. Exec keeps track of three "string classes"
simultaneously, class u, class v, and class vv. At any time,
164

COMPUTER TECHNIQUES AND PROCEDURES
the programmer can set any one of the string classes to
any one of seven levels. He can write, for example, "sscw
word," meaning to ^et the i'tring class u to have the value,
word. From that time on, until the instruction is super-
seded, all the subroutines that deal with the string class hierarchy u will consider the u strings to be words.
The procedure for designating tables is similar to that for designating strings. If the programmer would like to have programs written in terms of Tables x, y, and z operate on the contents of Table zones 2, 5, and 7, he
writes "Aztojc 2, ntoy 5, ntoz 7." * When Exec sees those
instructions, it does more than merely substitute 2 for x, 5 for y, and 7 for z. It finds the descriptions, in its file of table descriptions, that characterize the three numbered tables, and it substitutes these descriptions for the prepreviously prevailing descriptions of Tables x, y, and z,
respectively. When a subroutine operates on the contents
of the table, it examines the table's description and con-
trols its processing accordingly.
This makes it possible to accommodate diverse formats and conventions. Inasmuch as the adjustments are made "interpretively" during the running of the program, the user can change his mind and reprocess something in a sUghtly different way without having to go through extensive revision and recompilation of his programs. This is an advantage that the present technique has over the technique, based on the "communication pool," that has
--been developed in connection with the programming of
very large computer systems systems programmed by
teams so large as to discourage the effort to enforce the
* The italics are introduced here in the hope of bringing out the mnemonic significance of the code: "move n to x, and let n be 2." The programmer's typewriter does not have italic type.
165

EXPLORATIONS IN THE USE OF COMPUTERS

use of a single, standard set of conventions and formats.

The part of Exec that we have been describing is approxi-

mately an interpretive communication pool.

The third set of functions with which Exec is concerned

has to do with the display of alphanumeric information

on typewriters and on the oscilloscope screen. Although

these are very simple functions, they involve enough de-

tailed programming to be a nuisance unless they are

handled in a systematic way. Exec makes it convenient to

separate specification of the information to be displayed

from specification of the equipment through which it is

to be displayed. It uses standard programs to handle

strings that are long enough to be considered messages or

texts, but it provides special arrangements to facilitate

preparation of labels, headings, and the like. For example,

the programmer can call for the typing of any particular

character x on whatever typewriter is currently specified

to be typewriter b simply by writing "typ6 x." If the pro-

grammer wants the character to appear upon the screen of

oscilloscope a (there is only one oscilloscope now, but

we hope to have more), he writes "scpa x." With the aid

of Exec, the programmer can define in equally short in-

structions the size of the print, the vertical position at

which the text should begin, and other parameters of the

visual display. Exec's arrangements for displaying capital

and lower-case letters on the oscilloscope are primitive,

but it is a step in the right direction to have both capital

and lower-case letters. At present, a "lower-case" letter

Weis simply a small capital letter.

settled for that stop-

gap solution only in the interest of economy. The fourth and final set of functions handled by Exec

has to do with display, by the computer, of what the com-

puter is doing. One technique developed for this purpose,

166

COMPUTER TECHNIQUES AND PROCEDURES
a technique called "Introspection," will be described in a later section because it was developed as a separate
project. The arrangements described here are integral to
Exec.
One of the main causes of difficulty in man-computer interaction is that the computer does not give the man any good clues about what it is doing until it completes a segment of processing and spews forth the results. When
the computer is running, its lights flash so fast that they are scarcely interpretable. It seems important to provide a
way of having the computer give a running account of
its processing.
A --part of Exec called the "Reporting Subsection" --an optional part is brought into play each time a sub-
routine is called and each time a subroutine returns con-
trol to its caller. When the reporting subsection is brought
into action, it examines the list of things that it should do. This list can be changed while Exec and other programs are running. Ordinarily, the first thing on the list is to give the address, and, if it is available in the directory, also the name, of the subroutine that is being called or that is returning control to its caller. Since the subroutines operate very rapidly, the names and addresses would appear to be presented simultaneously, one on top of another, if they were shown in a fixed location on the screen. Therefore they are displayed in a format corresponding to that of a conventional outUne. If a chain of subroutines is called, each one operating at a level just lower than its caller, the names and addresses appear on successive lines of the display with increasing indentation. Then, as the subroutines return control, each to its caller,
the names and addresses are displayed again in such a way as to redisplay the outline pattern from bottom to top.
167

EXPLORATIONS IN THE USE OF COMPUTERS
To the display just described can be added, at the op-
tion of the operator, a display of the contents of the active registers of the computer. In addition, the operator
may see the contents of whatever parts of the computer's memory he wants to examine. He designates the various parts of memory to Exec by typing on the typewriter while the program is running. He can change his prescription at will. He may, for example, ask to see the
contents of Table x, the contents of Table 3, and the program of the subroutine itself. The current version of Exec allows him to specify nine different sectors of memory, either symbolically or in terms of absolute addresses.
When he indicates that he wants to see "the subroutine," Exec interprets "the subroutine" to mean the particular
subroutine that is being called, or that is returning control to its caller. That will, of course, be one subroutine
at one moment and another at another moment. When
the operator wishes to examine a table or a program in detail, he touches the space bar of the typewriter. That causes the system to pause in its progression through the sequence of things to be displayed, and to hold the current display until the operator releases it by touching the
tab key.
The Reporting Subsection provides a few additional
--conveniences minor ones introduced from time to time --on an ad hoc basis but the foregoing will suffice to
give an idea of the existing arrangement. Let us mention a few of the steps not yet accomplished, however. It seems worth while to connect to the Reporting Subsection the "Introspection" programs that will be described later. It is necessary to complete the arrangements that associ-
ate the tables {x, j, z, 1, 2, 3, · · · ) that reside in the
primary memory to corresponding structures in secondary
168

COMPUTER TECHNIQUES AND PROCEDURES
and tertiary memory and, in the manner of the Atlas
computer system, to arrange it so that information struc-
tures are automatically shifted up through the memory
hierarchy whenever they are addressed. It is necessary, also, to expand the mechanism that associates symbols with machine addresses. That mechanism is only a simple table-searching system, but it is inherently capable of
effecting the translation required to make conveniently readable the reports of "what is currently going on in
the computer."
We found it useful to distinguish, in Exec, between
"intrinsic" and "extrinsic" subroutines. Exec is highly "subroutinized" and has the partly hierarchical, partly recursive, structure that we have described as essential for procognitive systems. Each subfunction of Exec that appears to have any likelihood of proving useful in future applications is separated out and set into the form of
a subroutine.
--In the process of writing subroutines to handle sub-
stantive problems subroutines that made use of Exec
--but were not at first intended to be part of the Exec system we encountered repeatedly several sets or clusters of functions. By associating with Exec the subroutines prepared to handle those functions, we were able to build up a system of considerable convenience and power. The part of the system not intrinsic to Exec was too extensive to be held in primary memory at all times. However, it was clearly desirable to bring parts of it into primary
--memory coherent clusters of it corresponding to major --functions whenever required in the execution of a
program.
The easiest way to accomplish dynamic storage and
transfer of subroutines, and to handle the associated
169

EXPLORATIONS IN THE USE OF COMPUTERS

bookkeeping, was to take care of it automatically through

Exec's ability to examine calling sequences and subrou-
tine headings. We did not make much progress toward

that end during the course of the study. However, we did

work with the problem enough to see the great con-

venience and power that reside in a coherent structure of

computer subroutines and a largely automatic arrange-

ment for calling them and transferring information among

them. Evidently, the more sophisticated the arrangements,

the larger the fraction of the subroutines that will be in-

Wetrinsic to the arrangements.

visualize a system in a

continual process of development, with a set of intrinsic

subroutines, a set of extrinsic subroutines, and a continual

flow from the extrinsic set to the intrinsic set as more

and more functions are brought within the scope and

capability of the system.

On-Line Man-Computer Communication
"On-Line Man-Computer Communication" by Licklider and Clark (1962) discusses several problems in, and several steps toward the improvement of, interaction of men and computers. These include problems and de-
velopments in the use of computers as aids in teaching and in learning and as a basis for group cooperation in
the planning and design of buildings. The part of the paper that stemmed from the present study was the development of a pair of programs, referred to earlier as
"Introspection," that are closely connected with the lastdescribed major function of Exec.
The two programs of "Introspection" were designed
to demonstrate that, although present-day computers are opaque and inscrutable, of all the complex organisms and
170

COMPUTER TECHNIQUES AND PROCEDURES

systems in the world, computers are, in principle, the most

capable of revealing the intricacies of their internal proc-

Weesses.

consider this to be an important problem call-

ing for much research. Our two programs constitute only

exploratory steps.

The two parts of Introspection are "Program Graph"

and "Memory Course." Program Graph displays, in the

form of a graph relating that quantity to time, the con-

tents of any specified register or registers of the computer.

Memory Course displays the progression of control

from one memory register to the next during the operation

of a program. With the aid of these two programs, the

operator can see what is happening, as it happens, within
the processor and the memory of the computer. These

programs give him at once both a global view and a con-

siderable amount of detail. They let him see relations
among parts of the over-all picture. No longer is he con-

strained, as he has been with conventional procedures,

to peek at the contents of one register at a time, and to

build up the over-all picture from myriad examinations

of microscopic details.

To provide a rough impression of the operation of Program Graph, it may suffice to describe how it operates when it is set to display the contents of the register of the computer that is called the "program counter." The program counter contains the address of the memory

register that contains the instruction that is being exe-

cuted. In the absence of "branching" or "jumping," con-

trol proceeds from one register to the next, and the con-

tents of the program counter increase by one, each time
an instruction is executed. When a "branch" or "jump"

occurs, the number in the program counter changes by

some integral quantity different from one, and often the

171

EXPLORATIONS IN THE USE OF COMPUTERS
increment or decrement is rather large. Program Graph plots the graph relating the number in the program counter to the time. The display presents about a thousand individual quantities simultaneously to view. From the graph, it is easy to recognize the upward-sloping Hne segments that correspond to nonbranching, nonjumping
stretches of program. When the program "loops," as it
often does, branching backward and repeating a sequence of instructions over and over, the display shows a saw-
toothed waveform. When the program calls a subroutine,
the jump to the subroutine, the loops within the subroutine, and the return from the subroutine are all clearly
evident.
When Program Graph is used to display the contents
of the accumulator, the input-output register, or one of
the memory registers, the interpretation of the graph is, of course, quite different. In general, however, its main
value lies in its presentation of a large quantity of in-
formation in such a way that relations among parts are
easy to perceive.
The other Introspection program, Memory Course, displays only the course through memory followed by
the program under study. It shows that course as a succession of circles connected by a heavy line against a
gridlike background representing the primary memory of the computer. The grid upon which the display of Memory Course is shown consists of 4096 dots, arranged in 64 squares of 64 dots each, and representing one bank of
Amemory. register is represented by a very fine light dot
if the instruction and the address it contains are both zero. The dot is a little heavier if the instruction is not zero. The dot is a little heavier still if the address is not zero. If both the instruction and the address are
172

COMPUTER TECHNIQUES AND PROCEDURES
not zero, the dot is heavy. From the grid, therefore, the user can see which parts of memory are occupied and
which are not. In addition, after he has gotten used to
the display, he can make out which parts of memory
are used to store programs, and which parts are used to
store data.
When Memory Course is used to display the "trajectory" through memory followed by an object program,
the object program itself is not run in the usual way. In-
stead, the object program is operated by Memory Course,
which "traces" the progress of the object program and displays it on the oscilloscope screen. Each time an instruction is executed, a circle is drawn around the dot that corresponds to the location of the instruction in the com-
puter memory. When a program "loop" is traced, the line
is set over slightly to one side of the circles it has been connecting. That keeps it from retracing its path backwards and helps it represents the cycUc nature of the
course.
Memory Course represents loops, as just suggested, by tracing out a closed course. When the program transfers
control to a subroutine, a line jumps out from the dot that corresponds to the call and leads to the dot that corre-
sponds to the beginning of the subroutine. Thus, Memory
Course provides a simple, maplike representation of the
program structure. One can see where the various subroutines are, how long they operate, when they receive their calls, and when they return control to their callers.
If an error occurs, either in the computer or in the program, control is very likely to be transferred to an inappropriate location. If the user knows the structure of his program, either from having programmed it or from experience operating it, he sees that something unex-
173

EXPLORATIONS IN THE USE OF COMPUTERS
pected has happened. He then looks back to the begin-
ning of the unexpected Hne and determines precisely the location of the register within which the error originated. Having done that, he typically reruns the program, following its course very carefully as it approaches the critical point. If the error recurs, he reruns the program once more, this time stopping it at various points ahead of the critical one and using other means to examine the instructions, addresses, and data associated with those
points.
A File Inverter
The project to be described next was aimed, like Exec, at increasing the convenience and effectiveness with which the computer could be used in the study of library and procognitive problems. This project, however, had a much sharper focus than Exec. Its aim was simply to implement the operation called "file inversion."
A direct file is ordered with respect to its "items," and
usually several terms are associated with each item. An
inverse file is ordered with respect to its "terms," with several items usually associated with each term. Obviously, both the direct file and the inverse file are aspects
of a more general structure consisting of items, terms, and associations between items and terms.
The "File Inverter" is a computer program, written in
DECAL by Grignetti (1963Z?), that accepts a direct
file and produces an inverse file. Since there is no difference in abstract format between a direct file and an inverse file, the program produces a direct file if it is presented with an inverse one.
The file-inverting program includes a subprogram that
174

COMPUTER TECHNIQUES AND PROCEDURES
alphabetizes the entries. If it is used to invert a file consisting of terms associated with alphabetized items, it yields a file of items associated with alphabetized terms. If the items consist of the bibliographic citations of documents, and if the terms are the key words of the titles of the documents, then the result obtained by applying the file-inverting program is a kind of "permuted title index." Grignetti's program includes a subprogram that facilitates the selection of key words from titles (or
from abstracts or from texts). The subprogram selects from a string of words all those that do not appear upon a list of words to be excluded. The list of words to be excluded ordinarily contains the "function" words and, also, words that have been found not to discriminate.
An Automated Card Catalogue
Using parts of the file-inverting program, Grignetti ( 1963!j) prepared a program that automates some of the
functions involved in using an ordinary card index. The kind of card index toward which the program is oriented is not precisely the kind used in most libraries. It differs
mainly in assuming that each card will contain a series of descriptive terms. Such card indexes are found more frequently in documentation centers that specialize in laboratory technical reports and reprints than in libraries of books and serials.
The "Automated Card Catalogue" is a DECAL pro-
gram for use in exploration of card catalogue problems. The user sits at the computer typewriter and presents his retrieval prescription to the computer in the form of a Boolean function of the terms in which he is interested.
A person interested in non-digital simulations of neural
175

EXPLORATIONS IN THE USE OF COMPUTERS
processes, particularly including studies made under the
heading, "perceptron," but also other studies in the field of artificial intelligence, might type:
(artificial inteligence or perceptron or neural simulation) and not digital
Using the terms of the Boolean function as retrieval terms, the program searches a magnetic tape containing the "card" file. Whenever it finds one of the terms, it looks further within the entry to determine whether or not the function is satisfied. If the function is satisfied, the program displays the entire contents of the "card" on the oscilloscope screen for examination by the user.
Grignetti's program makes it convenient for the user
to correct his retrieval prescription, to reinitiate a search,
to find out just where he stands at any point in his study, and to save "cards" for future reference. The program "knows" the rules for regular pluraUzation and considers the search for a term to be satisfied if either the singular
or a calculated regular plural or a given irregular plural
of the term is found. In addition, the program works with a simplified system of spelling, as well as with literal spelling, and is therefore often able to find the desired term on a "card" even when the term is misspelled in the prescription. In such an instance, it displays, for example,
Do you mean "intelligence"?
The user then types y for "yes" or n for "no." The program remembers this answer and does not bother the user again with the same question. That may be convenient when the user is deafing with names he does not know very well, but it leads to comphcations that will have to be settled through further programming. Prob-
176

COMPUTER TECHNIQUES AND PROCEDURES
ably it will be better to correct the prescription than to perpetuate the indiscrimination.
A System to Facilitate the Study
OF Documents
The two programs described in the preceding sections are related to, and are intended for incorporation into, a system to facilitate the retrieval and study of documents. The "study" part of the over-all system is described in a report by Bobrow, Kain, Raphael, and Licklider
(1963).
The study system, called "Symbiont" because we hope
to develop it into a truly symbiotic partner of the student, displays information to the student via the typewriter or the display screen. It is intended as an exploratory tool,
for use mainly by students who are at the same time
experimenters, and it does not yet have the perfection or polish required for realistic demonstration or practical
application. However, it does make available, in a single,
integrated package, several functions that prove quite use-
ful to a student who wants to examine a set of technical documents, take notes on their contents, compare or
combine graphs found in different papers, and so forth.
Among the functions provided by Symbiont are the
following:
1. Present for examination a document specified by any sufficiently prescriptive segment of its bibliographic
citation.
2. Turn pages, forward or backward, in response to
the pressing of a key. 3. Permit designation of a passage (segment of text)
177

EXPLORATIONS IN THE USE OF COMPUTERS
by pointing to the beginning and then the end with a
light pen.
4. Accept labels from the typewriter and associate them with passages of text.
5. Record as a note, and preserve for later inspection, any designated passage.
6. Append bibhographic citations to extracted pas-
sages.
7. Accept retrieval prescriptions from the typewriter. 8. Accept from the typewriter coded versions of specifications of such operating characteristics as, "Consider a neighborhood to be five consecutive Hnes of text," or "Consider a search to be satisfied when any two of the three elements of the search have been satisfied." 9. Carry out retrieval searches and display passages in which the retrieval prescriptions are satisfied. 10. Compose graphs from tabulated data and present the graphs, against labeled coordinate grids, on the oscil-
loscope screen.
11. Set two graphs side by side to facilitate compari-
son.
12. Expand or compress the scales of graphs, under control from the light pen.
13. Change the number of grid lines or the calibration numbers associated with the lines, or both together, and recalculate and redisplay the calibration numbers when grid Hnes are added or deleted.
. The search routines used in finding desired passages of text operate with three sets of retrieval terms. The user
specifies the terms of each set initially through the typewriter. All the terms of a subset are considered equivalent during the search, and the search is satisfied insofar as
178

COMPUTER TECHNIQUES AND PROCEDURES
that subset is concerned if any one of the terms is encountered in the text. The user can specify whether he wants to find a passage in which at least one of the terms of one of the sets occurs, or a passage in which at least one of the terms of each of two of the sets occurs, and so forth. Even though this implementation is primitive, it is evident from preliminary experiments with Symbiont that automation of the function of searching for "ideas" will be a very powerful aid in technical study. Machine aid in manipulating graphs will also be very helpful.

Associative Chaining as an InformationRetrieval Technique

Most of the information-retrieval systems that have ac-

tually been developed, and even most of those that have

been subjected to intensive research, retrieve unitary

elements of information, such as documents, paragraphs,

Aor sentences.

basic point in Marill's (1963) paper,

discussed in Chapter 8, is that for many purposes the

retrieval of a unitary part of the corpus is inadequate, and

that what often is needed is an answer to a question that

may have to be derived through deduction from elements

of information scattered throughout the corpus. The as-

sociative chaining technique to be described briefly in

this section is a step in Marill's direction. It does not go as

far as the techniques described in the final two sections,

but it does go beyond the single, unitary element of the

corpus to explore "chains" of relation between one ele-
ment of the corpus and another. When the relation be-

tween two items is direct, they are said to be connected
by a first-order chain. When the relation between two

179

EXPLORATIONS IN THE USE OF COMPUTERS
items can be established only through the intermediary agency of a third item, the first two items are said to be connected by a chain of second order, and so forth.
In a report on "Associative Chaining as an Information Retrieval Technique," Clapp (1963) describes the idea of chaining as a general schema, then shows the correspondence between the chaining schema and certain schemata of graph theory, and finally discusses a program that traces chains of relevance through corpora
consisting of files of sentences.
Chaining, as a technique, is particularly simple and easy to discuss when it is separated from the problem of the nature of relevance. In Clapp's work, the two things
-- --the technique and the concept of relevance are well
separated. For purposes of simplicity and convenience, Clapp considers two sentences to be directly associated if they have one or more words in common. Thus, the sentences, "The cat is black," and "Black is a color," are directly associated. They have two words in common, "is" and "black." There is no direct, first-order association between the first two of the following sentences, but only a second-order association through the third sentence:
"The cat is black," "Fehne animals move gracefully," "A
cat is a feline animal." It is obvious, even at the outset, that something has to be done to inhibit associations
based on the common occurrence of frequently used verbs
and function words. In Clapp's approach, however, whatever is done about that is a separate matter from the development of the algorithm that traces out the chains.
Clapp's computer programs are divided into two sets. The first set of programs facilitates the preparation of a machine-processible file of information units, such as sentences, paragraphs, or documents. It then prepares,
180

COMPUTER TECHNIQUES AND PROCEDURES
from the file, a series of concordances. Finally, with the aid of the concordances, it determines the set of all firstorder associations. The second set of programs operates upon a retrieval prescription plus the set of first-order associations. The retrieval prescription is a set of words drawn from the vocabulary of the corpus. The first thing that the chaining algorithm does is to find all those elements of the corpus that contain all the words of the prescription. This is what a "conventional" informationretrieval system would do. Then, however, the chaining algorithm goes on to trace higher-ordered chains through the corpus and to retrieve the information elements that are involved in higher-ordered chains up to some cutoff order specified by the operator.
The program has been tested and demonstrated only with a corpus consisting of sentences. Except for minor
--considerations having to do with delimiters the clues --that mark stopping points such as ends of sentences or
paragraphs the chaining programs are not sensitive to
the distinctions among sentence, paragraph, document,
and so forth, and it is obvious that the chaining operation
can be carried out on textual strings of any class. How-
ever, pursuing the technique of chaining based on the
common occurrence of words beyond a level of the sentence does not seem to offer much promise. It is evident
that every book would be directly associated with almost every other book if the criterion were a word in common, and it is equally evident that almost no book would be associated with any other book if the criterion were a verbatim paragraph in common. For the technique of chaining, ordinary sentences seem to be ap-
proximately the optimal length. Fortunately, the sets of descriptive terms used in co-
181

EXPLORATIONS IN THE USE OF COMPUTERS
ordinate-indexing systems are of approximately the same length as sentences. The notion of association based on
inclusion of common terms is quite appropriate for them. It is in that domain that we think it most likely that the
chaining technique, and the chaining algorithms developed by Clapp, will find practical application.
In his exploration of the relations between graph theory and associative chaining, Clapp developed the chaining schema in considerably more depth than is reflected in this summary. For example, his development uses the number of parallel links as well as the order of
the links in the chain of association. Some of his ideas (but not the algorithms thus far programmed) recognize
gradations in the strength of association. That seems important because, intuitively, one thinks of relevance as capable of variation in degree.
The next step in the development of the concept of associative chaining, we think, should be an attempt to define the fundamental relatedness or relevance on which
the "association" is based. Associative chaining has a natural connection with the relational networks described in Part I and with the semantic nets and question-
answering systems studied by Marill and Black. The next step may, therefore, take the form of merging the chain-
ing concept with the concepts underlying the relational and semantic nets and the question-answering systems.
Two Question-Answering Systems
Marill's (1963) short paper on question-answering
systems, described eariier, initiated a series of studies that
involved a meld of symbolic logic and computer programming. Most of these studies were carried out by
182

)
COMPUTER TECHNIQUES AND PROCEDURES
Black, who described them in a series of memoranda and a report (1963). The memoranda and the report share
with the corpora of the question-answering systems a
tight, terse, logical quality that makes them attractive to the logician and difficult for the nonlogician to understand. Following is an effort to summarize, without gross distortion, two of the principal accompHshments of the work on question-answering systems in a freer and less formal exposition. One might justify this aim by quoting a paragraph from Black's "Conclusions on QAS,"
a memorandum dated November 13, 1963:
A string of words cannot be rephrased without significant loss
of facts or ideas relevant to some area. However, if we limit ourselves to certain areas, then the string of words can be
rephrased without loss of facts or ideas relative to those areas.
In the final paragraph of the same memorandum Black
goes on to say:
Before we can rephrase a string of words without significant loss, we must define our interests precisely. If we are interested in everything, then we cannot rephrase the string at all.
Let us say, therefore, that we are interested in assessing the possibility, and also the technical feasibility, of ( 1 representing large parts of the body of knowledge, as well as questions relating to the body of knowledge, in a formal language amenable to processing by a computer and (2) developing a system that will, by processing the questions and the stored corpus, deduce and display cor-
rect answers. Black's results attest to the possibiUty of doing those
things. However, Black's programs take a long time to determine the answers to fairly simple questions. That fact suggests that economic feasibiUty is dependent upon
183

EXPLORATIONS IN THE USE OF COMPUTERS
greatly increasing the processing efficiency of the ques-
tion-answering system or the processing speed of the computer, or both. The prediction made in Part I, that it is unlikely that there will be great increases in speed in
the same computers that have a greatly increased memory capacity, may not bear very heavily on this problem. It may be that we will use procedures that are fast, but not
very deep, to retrieve parts of the corpus that are rich in statements germane to a particular question, and then turn to deeper and slower procedures for the derivation of the answer from the rich informational ore.
The first of Black's two contributions to be summarized, the memorandum, "Specific-Question-Answering System," February 8, 1963, describes Version III of a system
written in the LISP language for the IBM 7090 com-
puter (McCarthy et al., 1962; Berkeley and Bobrow, 1964). In this system, the corpus consists of statements that are strings of ordinary words, symbols representing
--variables, and parentheses. The use of the ordinary words
is highly constrained so constrained that nothing can be said that could not be said equally well in the shorter, but less widely readable, notation seen in books on logic. The only variables are XI, X2, X3, what, when, which, and how. The parentheses have the effect of forcing the system to consider as a unit the string within the paren-
theses.
The "questions" asked of the Specific-Question-Answering System may be either statements, in which case they are confirmed or denied by the system, or ordinary questions containing the variables, XI, X2, X3, what, and when, etc. The answer elicited by a "yes-no" question is "yes," "no," or "no answer." The answer to any
184

COMPUTER TECHNIQUES AND PROCEDURES
Other question is a list of items that constitute a correct
and reasonable reply, or "no answer."' The system seeks answers to questions by processing
the questions and the corpus in a very straightforward, rigorous way. It looks through the corpus for a statement that is the same as the statement that constitutes the question (in the case of questions in statement form) or that can be transformed into the question by removing a "not." If it finds a match, the answer is "yes." If it finds a negated match, the answer is "no." If it finds neither, it looks for a conditional statement in the corpus in which the consequent matches the question. If it finds such a statement in the corpus, it undertakes to determine an answer to the subsidiary question, whether or not the premise of the conditional statement is true. Proceeding in this way, it tries every possibility of deriving the question or its negation from the statements of the corpus.
The procedure for processing of questions containing variables is a little more complex than the procedure just
described. It is necessary, in seeking an answer to a question containing a variable, to keep track of all the individuals (people, objects, etc.) that can be values of the variable. The process amounts, approximately, to determining the list of individuals that meet all the conditions that are imposed upon the variable.
The system is capable of answering not only simple,
single-variable questions, but also multiple questions (conjunctions of simple questions), conditional questions (containing if . . . then . . .), and even questions con-
taining the names of LISP computer programs. In the latter case, there is a rigid format that must be followed in giving the name of the program and its arguments.
185

EXPLORATIONS IN THE USE OF COMPUTERS
All the foregoing structures mentioned as acceptable question forms are also acceptable as forms for state-
ments in the corpus. In the corpus, a program name may
occur even in the antecedent of a conditional statement.
We mention these things to indicate that the system has
the capability of expressing complex relations and of deriving answers to complex questions.
To see approximately what the system does, let us consider a few oversimplified examples and one more
complex example. Suppose, first, that the corpus consists merely of two statements:
MERCURY IS (A PLANET) IF (XI IS A PLANET) THEN (XI IS A PLANET OF THE SUN) The question asked of the system, in statement form, is:
MERCURY IS A PLANET OF THE SUN To that question, the system says, simply:
YES
Suppose, for the second example, that the corpus consists of only one sentence:
EARTH IS SMALLER THAN JUPITER
The question asked of the system and the foregoing rudimentary corpus is:
JUPITER IS SMALLER THAN EARTH
The answer given by the system to that question is:
NO ANSWER
But now suppose that a second statement is added to the corpus. The corpus now consists of the two statements:
186

COMPUTER TECHNIQUES AND PROCEDURES
EARTH IS SMALLER THAN JUPITER IF (XI IS SMALLER THAN X2) THEN (X2 IS NOT SMALLER THAN XI)
The question is still:
JUPITER IS SMALLER THAN EARTH
The system is now able to determine an answer. It says:
NO
This example illustrates one of the basic notions under-
lying Black's work: It is possible, and it may be highly
desirable, to put most of the "inteUigence" of the system into its corpus and to let the processing program itself retain a high degree of simplicity and, if the term is appropriate, formal elegance. As will be seen, the same notion appears in "Ontogeny," to be described later, even though Ontogeny is approximately the antithesis of Black's system in respect of rigor and tightness of formal-
ization.
The final example involves a corpus consisting of eight direct statements and three conditional statements. They
are:
MERCURY IS NEXT SMALLER THAN PLUTO PLUTO IS NEXT SMALLER THAN MARS MARS IS NEXT SMALLER THAN VENUS VENUS IS NEXT SMALLER THAN EARTH EARTH IS NEXT SMALLER THAN NEPTUNE NEPTUNE IS NEXT SMALLER THAN URANUS URANUS IS NEXT SMALLER THAN SATURN SATURN IS NEXT SMALLER THAN JUPITER IF (XI IS NEXT SMALLER THAN X2) THEN
(XI IS SMALLER THAN X2) IF (XI IS NEXT SMALLER THAN X2) AND
(X2 IS SMALLER THAN X3) THEN (XI IS SMALLER THAN X3) IF (EARTH IS SMALLER THAN XI) THEN (XI IS A MAJOR PLANET)
187

EXPLORATIONS IN THE USE OF COMPUTERS
The question asked of the system and this corpus is:
WHAT IS A MAJOR PLANET
The answer provided by the system is:
NEPTUNE URANUS SATURN JUPITER
This last example would be more impressive than it is if the corpus contained a large number of irrelevant statements in addition to the statements shown. The presence of irrelevant statements would increase the length of time required by the computer in answering the question, but the computer has the great advantage, in operations of
this kind, that it does not tend to forget the relevant facts already found while it is examining the irrelevancies. For
a human being, on the other hand, a problem of the
present kind that is difficult but nevertheless within one's scope of capability becomes entirely hopeless as soon as
a large amount of irrelevant material is introduced. That fact, we believe, is significant in its bearing on the prob-
lem men face in drawing answers from the body of knowledge that is now held in libraries and document rooms.
The other paper of Black's that we shall discuss here is "A Question-Answering System: QAS-5" (1963).
This paper describes in detail the operation of a latergeneration question-answering system, a descendant of
the Specific-Question-Answering System that we have been discussing. The main advances made in the interim
between the two papers were advances in the handling of quantification and advances achieved by formaUzing the language approximately in a way suggested earlier by McCarthy (1959). The advance in quantification makes
188

COMPUTER TECHNIQUES AND PROCEDURES

it possible for the system to deal with problems involving

"some" and "all." The formalization of the language

makes it difficult for the uninitiated reader to understand

what is being done, but it reveals the flaws and pitfalls to

the veteran in a clearer way than the more readable lan-

guage does, and, moreover, it suggests what to do to cor-

Werect or avoid them.

consider the formaHzation, there-

--fore, to be a step more in a right direction than in a wrong
one a step that must be taken in order to reach a posi-

tion from which it will be possible to move forward to

simultaneous readability and formal effectiveness.

The mode of operation of QAS-5 is similar in basic

principle, though somewhat deeper and more complex,

to the mode of operation of the Specific-Question-Answer-

ing System. Some of the flavor of the method is given by

the following protocol:

Step 1 : The system finds the first match for question 1

in statement 6.

Step 2: The system forms the backward transform of

--question 1 and statement 6, giving a new condi-

tional (7)

at (desk, y), at (y, country) -^ at

(desk, country).

Step 3: Step 4:

--The system sets up the first antecedent of (7)

as a new question (2)

at (desk, y).

The system finds the first match for question 2

in statement 2.

Step 5: The system forms the transform of question 2

--and statement 2, giving the answer to question
2 (I) at (desk, home).

The latter would be read, as one might possibly guess,
"I am at my desk at home."
The problem to which Black's QAS-5 report is wholly

189

EXPLORATIONS IN THE USE OF COMPUTERS
dedicated is a problem posed by McCarthy in 1958 and hitherto not solved by any nonhuman system. It is a well known problem in artificial-intelligence and heuristic-programming circles and is called the "airport problem." The problem, stated here informally, is fairly simple:
I am at my desk, at home. My car is in my garage, which is also at my home. I want to go to the airport. The airport is in the same county as my home. I can walk from any point
that I would call "at my home" to any other point that I would also call "at my home," because, of course, the dimen-
sions of the area subsumed under "home" are not very great.
I can drive from any point in my county to any other point in my county. What should I do?
The answer to the question, or the solution to the
problem, is said to be:
I should go from my desk to my garage on foot and get my car, and I should then drive my car from the garage to the
airport.
Having stated the problem and given the solution, we
should perhaps repeat that, although the answer is obvi-
ous to any adult human being who understands English,
no one had succeeded in devising a wholly automatic system that would derive the answer (or a formal statement corresponding to the answer) from the description of the situation and the statement of the question (or formalizations of them). Black's report gives a step-by-
step account of the procedure used by QAS-5 in solving
the problem. In addition, it displays, point by point, the minor differences between the notation suggested by McCarthy and the notation employed by Black.
The conclusions that we draw from our experience with question-answering systems are summed up in the assertion that the achievement of Black's program in
190

.
COMPUTER TECHNIQUES AND PROCEDURES
solving McCarthy's problem is simultaneously a signal
advance in automated question answering and a common-
place performance for a moderate intelligence. In greater detail, the conclusions are:
1 Clear progress is being made in bringing logical de-
duction within the scope of automation.
2. In the process of programming a system to accomplish a feat such as the one described, one begins to see
how extremely deep and complex are the intellectual processes that one accepts as commonplace and undemanding of intelligence when those processes are carried
out by people. 3. In the running of such programs, one begins to
sense the magnitude of the gulf that separates a demonstration of the type just described from an economically feasible operating system. As the problems become more complex, and as the corpus becomes larger, the amount of time required for processing goes up steeply. This is a discouraging counterpoise to the pattern of growth of the
information-processing technology described in Part I.
4. At the same time, one sees, even at this stage, many ways in which processing can be made more efficient, and
-- --one senses that there are waiting to be discovered
ways of formulating the procedure that are much more
powerful than the ways thus far employed.
In short, it appears to us that the domain of questionanswering systems is an intellectually deep and technologically demanding area for research and development. As suggested, there is an extremely long way to go before useful answers can be deduced from extensive informa-
tion bases at reasonable cost. On the other hand, it may
well be that, in this area, each basic conceptual advance
191

EXPLORATIONS IN THE USE OF COMPUTERS
will be a long stride toward the procognitive systems we
envision for man's future interaction with the fund of knowledge.
An Approach to Computer Processing
OF Natural Language
This final project was pursued intensively during the
first year of the study, but, for reasons not related to its
degree of promise, it lay dormant during the second year. Although the project does not appear to be worth con-
tinuing in its present form, the following description may
prove useful.
--The approach selected at the outset to try to mirror
in computer programs the ontogenetic development of
--the human ability to generate and understand language was quite different from the approach, then more popular, based upon syntactic analysis. The approach adopted paid more attention to semantics than to syntax. However, many of the investigators who earlier had concentrated on syntactic analysis have directed their efforts toward semantic analysis, and what seemed to us at the outset to be an unpopulated field is rapidly becoming crowded. That fact, together with our sharpening awareness of the very great difficulty and even greater extent of the task, account for the negativeness of our thoughts about reactivating "Ontogeny."
At the beginning of the project, it seemed to us to be a good idea to start with "baby talk" and to try to re-
capitulate, as closely as possible, the development of the
human language process. Recognizing the importance of
the "verbal community" in each individual's development
192

COMPUTER TECHNIQUES AND PROCEDURES
of language process, we set up a situation in which an
operator at the typewriter played the role of the verbal
community and, acting as stimulator, instructor, reinforcer, umpire, and protector, presided over the "shaping up" of language behavior in the computer.
It was necessary, of course, to provide the computer with basic structures and capabilities corresponding
roughly to those that would be inherited by a human being. It was necessary also to set up some domain of
discourse that would be potentially "meaningful" to the computer, as well as to the operator, and that would pro-
vide an analogue to the "environment" in which human
beings behave and with reference to which most of their
-- --language that is not about themselves is oriented. --One part of the internal mechanism of the system
--of computer programs seems worth describing despite
the fact that its nature does not in any direct way determine the nature of the over-all system. This part of the program is concerned with the representation, in the computer memory, of the words and phrases communicated between the operator and the computer. In the input and output equipment, the words and phrases take the form of strings of characters or character codes. The
codes are the so-called "concise" codes for alphanumeric
characters employed in the PDP-1 computer. Each code
is a pattern of six binary digits. Representation of words, phrases, and so forth, as
strings of coded characters is inconvenient and uneco-
nomical for many information-processing purposes. In a
computing machine that has registers of fixed length, it is inconvenient to have words and phrases of variable
length. We were at the outset not so much concerned
193

EXPLORATIONS IN THE USE OF COMPUTERS

with economy of representation as with convenience of

processing, and we adopted an approach designed mainly

Wefor convenience.

represented each word, or phrase,

or sentence, or string of any recognized class, by a 36-
bit code. The code was made up of a 30-bit main code

and 6 bits of auxiliary information, which included desig-
Anation of the class to which the strins; belonged. 36-bit

code can be stored conveniently in two consecutive regis-

ters of the PDP-1 memory.

The rule for representing incoming words in the computer memory was the following. If the word consisted of

five characters or fewer, the concise-code representation

(filled out with the six auxiliary bits and with "filler
characters" if necessary to make it come to a total length

of 36-bits) is the computer representation; if, on the other hand, the word contained more than five characters,

then the computer representation consists of the concise

codes of the first three characters, the six auxiliary bits,

and, in addition, a 12-bit "hash code" calculated by a

rather complicated procedure from the concise codes of

the remaining characters. This representation is capable
of discriminating among about 4000 different words with

the same three leading characters. Because the calculation

of the hash code is carried out by a procedure akin to

the generation of "random numbers," one cannot be en-

tirely sure that two different words will not yield the same code. Nevertheless, he can make the probability of a "col-

lision" as low as he likes by selecting a sufficiently long

representation.
In the initial stages of the work, we were not much

concerned about accidental confusion of one word with another. Children certainly confuse words. Indeed, we

194

COMPUTER TECHNIQUES AND PROCEDURES
were attracted by the hypothesis that some of the confusions that arise in human communication and thinking are attributable to something hke a hash-code process in
neural representation.
The agent that converts strings of text into hash codes is, of course, a computer program. First it divides a string of text into words and determines a code for each word. Then it combines the words into phrases, using punctuation as a guide, and determines a hash code for each phrase from the codes for the words within the phrase. Then it determines a hash code for each sentence from the codes for the phrases within the sentence, and so forth. Thus, for each word, for each phrase, for each sen-
tence, . . . , there is a 36-bit representation. After the conversion to this internal code has been effected, and until a stage is reached at which it is necessary to gener-
ate a response in the form of a string of alphanumeric characters, all the processing is carried out with the in-
ternal 36-bit codes.
It is easy to transform alphanumeric text into internal
codes. To do that, it is necessary only to apply the trans-
formation programs that calculate the codes. However,
--to transform in the other direction to go from the in--ternal code representation to a string of alphanumeric
characters is another matter. Because information is sometimes lost in the forward transformation, it is not possible simply to calculate the reverse transformation. It is necessary to employ a "table-searching" procedure. However, it is certainly neither necessary nor desirable to store every string of characters received in order to have it ready to type as a response. If one is to respond in a natural way, he must be able to generate sequences
195

EXPLORATIONS IN THE USE OF COMPUTERS
of words that he has never received. Moreover, there are
too many strings of words to consider storing them all in a computer memory. The procedure adopted, therefore, is to associate with each internal word code, but
not with the code for any string of any class other than word, its complete concise code, i.e., the string of concise codes corresponding to the characters of the word.
The association is achieved in the following way. All the internal codes, for words, phrases, sentences, and so
--forth, are kept together along with other information -- in a table called the "Hash Table." One of the entries
in the Hash Table, for each word represented in that table, is the address of the register in the Vocabulary Table in which the corresponding concise-code representation begins. That makes it possible, given the internal
code corresponding to a word, to find the corresponding concise code and to have the word typed on the computer
typewriter.
For those internally represented strings that are not merely words, there is still another table, called the "Subaddress Table." The entry in the Hash Table that is associated with a sentence the way the Vocabulary Table address is associated with a word, is the address of a register in the Subaddress Table. At that address in the Subaddress Table, one finds the beginning of a list of "subaddresses" that are addresses of registers back in the Hash Table. In those registers in the Hash Table are the entries for strings of the next lower class. (Since this example started with a sentence, they are entries for phrases.) With each hash code for a phrase is associated the address of another register in the Subaddress Table. Going back to the Subaddress Table with that address, one
196

COMPUTER TECHNIQUES AND PROCEDURES

finds addresses of registers in the Hash Table. Finally, in

the designated registers in the Hash Table are addresses

of registers in the Vocabulary Table. In the Vocabulary

Table, of course, are the concise codes of the words.

The procedure just described is implemented by pro-

gramming, so no effort of thought is involved after the

program has been perfected. The program runs much

more rapidly than the typewriter can type, and there is

therefore no observable delay. With the system, one can

start out with a 36-bit hash code and wind up with a long

typewritten sentence. If the initial code is the code of a
paragraph, indeed he winds up with a paragraph. We

have checked the system to that level of operation. Obvi-

ously, nothing stands in the way of representing an entire

book with a 36-bit internal code. However, one cannot

uniquely represent the individuals of any set of size ap-

proaching 2" with hash codes n bits in length. Our selec-

tion of 36-bit codes, and our compromise in the direction

of readability by man as well as by machine, was con-

ditioned by the fact that we were working with a "young"

language mechanism that would not be expected to de-

velop a very large vocabulary for some time.

It is now doubtless evident that a description of com-

puter programs in ordinary language encounters serious

Weproblems of exposition and endurance.

shaU, there-

fore, not describe the entire Ontogeny program in as

great detail. Let us, nevertheless, explain how the system

is designed to keep track of the properties of the various

words and phrases and the entities and operations for

which they stand.

The repository for factual information, in Ontogeny,

is a table called the "Property Table." One of the entries

197

EXPLORATIONS IN THE USE OF COMPUTERS
in each section of the Hash Table is the address of a corresponding section in the Property Table. For convenience, the Property Table records the corresponding Hash Table address and also the internal code of the string with which the properties are associated. The properties them-
selves are represented by internal codes. When it is neces-
sary to determine the meanings of the property codes, one has to find the codes in the Hash Table and go on from
there in the way just described. The structure within which properties are represented
in the Property Table is a simple hierarchy, an "outline." The rules for fisting properties are loose. In the main, they
were made up as problems arose, and indeed a certain amount of care was taken not to create a sharp, formal, rigid system. Syntactic and semantic properties are mixed
indiscriminately. In the basic system, there is not even any distinction between the symbol and the thing for
which it stands. That is to say, under "table" we might
record the property of being used mainly as a noun, the property of being used sometimes as a verb, and the
property of usually being made of wood. The representation of this last property may take the form:
table material
wood
usually steel
sometimes
However, the system would be expected to function without great difficulty if, through happenstance, the arrangement were set up as:
198

COMPUTER TECHNIQUES AND PROCEDURES
table material usually
wood
sometimes
steel
We did not reach the point at which programs actually
operated with that kind of irregularity of format, but we did have search programs that examined the "next level down" if they did not find a satisfactory property on the
level initially assigned.
From the description thus far, it may be evident that
the Property Table is, by nature, full of circular defini-
--tions. Everything is defined in terms of something else
except for a relatively few primitives that are associated
with subroutines. One of the properties of "move," for example, is that move is often used as a verb. Another is that, when it is so used, it is to be implemented by exe-
cuting a subroutine that is capable of taking arguments
that answer "what," "by whom," "from where," and "to where." Some of the properties of "pencil" refer to its
Acapability of serving as an argument. pencil is "mov-
able," "takable," "bringable," and so forth.
We are now almost in a position to turn our attention
to the procedure through which an incoming message is
processed and responded to by the computer. One more
part of the system must be described, however, before that can be done conveniently. This remaining part is the one that has to do with the "domain of discourse" mentioned earlier.
The domain of discourse is a model room equipped with a few items of furniture. The room has a door that
199

EXPLORATIONS IN THE USE OF COMPUTERS
can be opened to various degrees, a window that can be opened or closed, a table that can occupy any otherwise unoccupied position within the room, and a chair subject to the same constraint. There are a book and a pencil, to be manipulated, an active agent called "Comp," and another active agent called "Oper." The discourse in-
volves Comp and Oper and is actually carried out by
the computer and the operator. The room and its contents are represented in the
computer memory, of course, and they are also represented diagrammatically by simple line drawings on the
screen of the oscilloscope. When the door is opened, the representation of the door in the computer memory
changes, and the schematic door on the oscilloscope screen (a straight line with a little figure near one end representing the door knob) swings.
The basic subroutines, corresponding to operations in the domain of discourse, are implementations of "move," "go," "carry," "bring," "open," "close," "put," etc. These
subroutines, together with the subroutines that handle the encoding and decoding, the search for properties and the
analysis of input messages, were all that we actually prepared and operated. The plan encompassed two additional classes of subroutines. The first of these was to
handle the addition, deletion and modification of properties, under the control of input messages. The second was to handle the addition and modification of subroutines,
again under the control of input messages. If we had been able to carry through to some accomplishments in the first additional category, we should have been able to
--increase the verbal capabihty of the system, but only by
adding to its knowledge to its vocabulary and its fund of facts. If we had been able to move on into the second
200

COMPUTER TECHNIQUES AND PROCEDURES
additional category, we should have had within our grasp
the capability of achieving almost unhmited restructuring
and reorganization of the system. But we did not accompHsh either of those things, and we mention them here only to indicate that the approach had a higher aspiration than merely to move line diagrams about on the screen
of an oscilloscope.
Now, at last, we come to the procedure employed in
analyzing the incoming messages and selecting and directing the actions taken in response to them. The re-
sponses were, as suggested earlier, to move things about
-- --in the room, to make replies by way of the typewriter, and in hope but not in actuality to add to the internally stored knowledge and to the internally stored behavior patterns. By knowledge, of course, we mean the contents
of the several tables mentioned earlier. By behavior patterns, we mean the set of subroutines available for use in
responding.
The problem of interpreting an incoming message is, in the approach we have been describing, to select the appropriate subroutine or patterns of subroutines and to
find the arguments that they require under the prevailing
circumstances. The selection of subroutines is guided by associating subroutines with verbs. The search is carried out by a part of the program that examines the internal codes that represent the incoming message and a list of roles that the message segments may play. Records are kept in a matrix during the processing of a message. The rows of the matrix are associated with the words of the incoming message. The columns of the matrix are associ-
ated with the possible roles.
In the version of Ontogeny that was carried to the point
of demonstration, the processing deals only with words.
201

EXPLORATIONS IN THE USE OF COMPUTERS
The first step is to look up each word of the incoming message in the Property Table and place a tally in each
cell of the matrix that corresponds to a function that the
word can fulfill. When this has been done for all the
words of the message, the task becomes one of finding an appropriate and consistent assignment of words to functions and, at the same time, a correspondence between the functions and the argument requirements of a subroutine that goes with the verb.
The procedure used to carry out this task starts by "freezing" the rows and columns of the matrix that contain only a single tally. The next step is to prepare simpler matrix patterns in which each of the words at first associated with two or more roles is assigned to a single role. These simpler matrixes are then considered one at a time.
The subroutines corresponding to the word assigned
to the verb category in the first simplified matrix are ex-
amined. If one of them has a set of argument requirements that match the roles to which words are assigned, then that subroutine is selected, the arguments are supplied to it, and the response is executed. In an effort to get the system into operation quickly, we satisfied ourselves with the first subroutine that met the requirements. If no subroutine met the requirements of the first assignment pattern, the second assignment pattern was used, and so on. As soon as a suitable subroutine was found, supplied with arguments, and executed, the response was considered accomplished. The program then simply went into a "listening" mode and waited for the operator to
take the next step.
Toward the end of the work on Ontogeny, we were planning a set of subroutines that would operate on higher-echelon strings than words. With this set of sub-
202

COMPUTER TECHNIQUES AND PROCEDURES
routines, there was to be associated a subsystem for keeping track, in a primitive way, of the "situation." The system was to be capable of asking, on receipt of a message,
"Am I already familiar with this message in this context?"
If so, it was to inquire of itself what response it had previ-
ously made and how effective the response had been. If
--the result had been sufficiently favorable, then accord--ing to the plan the system would simply have made
the same response again and taken notes on its effect. In the likely event that no record existed of previous
experience with the over-all message in the prevailing context, then the projected system would work with lower-echelon segments of the message, hoping to find that one or more of them was already "understood." In the absence of usable prior experience at each echelon,
the system would drop down to the next-lower echelon until it finally came to words. Failing to understand a
word, or failing to understand a phrase given experience with the words of the phrase, it would ask for help.
Our experience with Ontogeny left us with five main impressions: (1) It seems possible, and even likely, that we could store up enough substantive information in a computer memory to handle the analysis of natural lan-
-- --guage semantic as well as syntactic an analysis ca-
pable of supporting "reasonable" responses, if only the
domain of discourse is not very wide. (2) It is probably more important to limit the domain of discourse than to
limit the length or complexity of the input messages.
(3) Many so-called semantic properties play roles that
are almost indistinguishable from syntactic roles. The dis-
tinction between things that are capable of acting with initiative as voluntary agents and things that are not, for example, seems to be approximately as important as the
203

EXPLORATIONS IN THE USE OF COMPUTERS

distinction between the active voice and the passive voice

Aof verbs. (4)

sympathetic, cooperative, verbal, com-

munity is a fundamental essential for the development of

a sophisticated verbal mechanism. To develop complex

language behavior in a neutral environment would, we

think, take another long-suffering recapitulation of evolu-
tion. (5) On the other hand, no one seems likely to de-

sign or invent a formal system capable of automating

sophisticated language behavior. The best approach,

--therefore, seems to us to be somewhere between the ex-
tremes to call for a formal base plus an overlay of

experience gained in interaction with the cooperative

verbal community.

204

A

