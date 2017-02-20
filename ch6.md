CHAPTER SIX
Research on Quantitative Aspects of Files and Text
Two STUDIES by Grignetti (1963^, 1964) deal with quan-
titative aspects of representations of information in digital
memories. The first study concerns the average length of representations of descriptions of documents or, in greater
generality, the average length of representations of "terms" (e.g., of descriptors associated with documents).
The second concerns the informational measure "en-
--tropy" or, to look at it the other way around, the --redundancy of EngHsh text considered as a string of
words. Thus both studies bear upon the amount of mem-
ory required to store library information: the first with indexes, the second with actual text.
142

quantitative aspects of files and text
On the Length of a Class of Serial Files
From one point of view, the over-all organization and
concept of a library or of a procognitive system is a more
important thing to grasp, or to improve, than is the effi-
ciency of a low-level "detail" function. On the other
hand, a few functions that appear from one point of view to be mere details, to occupy low levels in the over-all system, are seen from another point of view to be both
basic and ubiquitous. One of these functions that looks
like a technical detail from one standpoint and like something very basic and general from another is the encoding
of elements of information for storage in a digital mem-
ory. Let us, for the purposes of this discussion, adopt the
point of view from which it seems important. As soon as we do that we may be prepared to examine subcategories, and one of the most conspicuous of these is the subcategory that includes catalogues and indexes. The study to be summarized deals with such files of information.
Perhaps the best schema to keep in mind while thinking about this problem is the schema of an index consisting of the names or numbers of the documents in a collection and, associated with each name or number, a list of
terms or descriptors that characterize the corresponding
document according to some coordinate indexing system.
The problem under consideration is how to encode the terms. The object is to be economical in the use of storage space and, at the same time, to make it easy for a com-
puter to decode the representation and determine the names or numbers (or addresses) of specified documents.
One of the most widely used techniques for represent-
ing terms is simply to spell them out in full or to record readable abbreviations of them. The direct way to encode
143

)
EXPLORATIONS IN THE USE OF COMPUTERS
such representations for storage in digital memory is to
assign a binary code to each character in the character ensemble and to store the binary code patterns. That
technique has the disadvantage of using much more mem-
ory space than is necessary. This kind of inefficiency is the subject of the study to be summarized in the next
section.
A technique that is more economical of memory space
is to number all the terms that may be used and to represent in memory in association with each item, not the
corresponding terms themselves, but the numbers that were assigned to them. Since there are sometimes several terms per document, it is important not to let the numbers that represent different terms run together in such a way
as to preclude subdivision of the over-all representation
into its parts. The encodings of the sets of terms associated with different documents must also be kept separa-
ble. In the past, people have kept codes separable either by using special characters as separators or by adding
enough leading zeros to the short codes to make all the codes the same length. (Fixing the length of the codes
takes care only of separations within the set of terms associated with a given document, and not of separations between the sets of terms associated with different docu-
ments, but we may for the sake of simplicity limit our
consideration to the problem of intraset separation. The prevailing opinion has been that the use of separa-
tors leads to more compact files than the use of fixedlength codes. The first thing Grignetti did was to analyze that comparison (1963fl). It turned out that, on the average, and under certain reasonable assumptions, the fixed-length code is actually shorter than the variablelength code plus separator. If one thinks about this ques-
144

QUANTITATIVE ASPECTS OF FILES AND TEXT
tion with simple, schematic examples in mind, he is likely to doubt this conclusion of Grignetti's and to agree with
the prevailing opinion that Grignetti finds incorrect. How-
ever, Grignetti's conclusion becomes quite obvious as soon as attention is focused upon large filing systems in which the list of legal terms is long. Consider, for example, that, of a list of nearly 1000 terms, almost 90 per cent would be represented by three-digit codes. About 9 per cent would require one leading zero, and about 1 per cent would require two leading zeros to bring them up to
the "fixed" length of three digits.
In his work on coding efficiency, Grignetti also examined the notion that products of prime numbers might provide the basis for an effective coding system for the purpose we are considering here. In such a system, each term would be assigned a prime number, and the set of terms associated with a particular item would be represented by the product of the prime numbers associated with the members of the set. Grignetti was able to show conclusively that the prime-number code is an inefficient code, less good than either variant of the elementary system considered in the foregoing paragraphs.
The preliminary inquiries just described led Grignetti
to look for a truly efficient coding system for terms
(1964). He found one. He calls it the "combinational
code." It is fairly easy to construct a combinational code.
First, one has to decide the maximum number of terms
that will be associated with an item, say, five. Second, he examines the list of legal terms, numbers the individual terms, and makes up all the possible combinations of term numbers, taken five or fewer at a time. Third, he orders the numbers corresponding to the terms of each combination (each set of five or fewer) in a sequence of
145

EXPLORATIONS IN THE USE OF COMPUTERS
increasing magnitude. Fourth, he reorders the list of combinations according to a criterion that takes into account primarily the magnitude of the largest number in the subset but also, secondarily, the number of numbers in the subset. Finally, he assigns integers in increasing sequence to the members of the reordered list. Grignetti gives an analytical procedure for encoding and decoding.
He points out that the procedure does not have to be
changed, and that existing code numbers do not have to be altered, when new terms are added to the list of legal terms. Finally, he shows that the combinational code is
the shortest possible code.
Entropy of Words in Printed English
Grignetti's interest was attracted to the question of the representational efficiency of direct encodings of the strings of words that constitute text by the consideration, discussed in Part I, that storage of the body of knowledge in processible memories will be an important basis for procognitive systems (Grignetti, 1964). In order to estimate the representational efiiciency, it is natural to compare determinations of the number of bits required to store a typical segment of text with estimates of the actual (Shannon-Wiener) information content of the text. The classical estimate of the information measure of a typical word of text is the one made by Shannon in 1951 on the assumption that the frequency of occurrence of word types is sufficiently approximated by Zipf's famous law. Shannon's estimate of the information measure, or entropy, was 11. 8 2 bits per word. However, Bemer (1960), using roughly the approximation that Shannon used, calculated that words could be stored, on the average, in
146

QUANTITATIVE ASPECTS OF FILES AND TEXT

--10.76 bits of memory space with the aid of a com-

pression code that was obviously not optimal. That led

Grignetti to examine Shannon's results closely.

By a method slightly different from Shannon's, a

method that seems straightforward and in which no flaw

has been detected, Grignetti found the information meas-

ure to be 9.7 or 9.8 bits per word.

From one point of view, the difference, which is only

2 bits per word, does not seem likely to have much prac-

tical significance. From another point of view, however,

the important question is whether or not further work on

encoding of text seems to be intellectually attractive. If it

seems attractive, then it is possible, and perhaps likely,

that a coding scheme will be found that is highly efficient

in use of memory space and, at the same time, economical

Onin respect of processing.

the other hand, if further

work is not intellectually attractive, there is not likely to

be an increase in either the efficiency of the use of space

or the economy of encoding and decoding. Perhaps the

2 bits per word will have a stimulating effect. Clearly, the

point on which study should now concentrate is the sim-

plification of encoding and decoding.

147

