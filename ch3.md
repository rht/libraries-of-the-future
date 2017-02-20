CHAPTER THREE

Information Storage,
Organization, and Retrieval

The purpose of this section is to focus briefly on basic

concepts of the field of "storage and retrieval" that seem

particulariy relevant to procognitive systems. Some of the

ideas of this field have already been mentioned in our

example in which documents were retrieved with the aid

Weof descriptors and a thesaurus.

have also illustrated

--applications of passage-retrieval and question-answering
techniques techniques that penetrate the covers of

documents and deal with sentences and paragraphs or

with "ideas" and "facts." Let us now examine those and

related techniques a bit more systematically.

The basic unit of knowledge appropriate to our pur-

poses may well be akin to the "idea" of popular and

sometime philosophical usage, but we shall not try to ex-

70

STORAGE, ORGANIZATION, AND RETRIEVAL
ploit that possibility because "idea" is discouragingly
nebulous. Alternatively, the basic unit may be closely re-
lated to the mathematical concept of "function," or to the logical concept of "relation" that figured centrally in our earlier discussion of relevance networks. Again alternatively, the logical systems of predicate calculus, particularly the so-called higher-order predicate calculi, offer formalisms for the expression of complex attributes
(predicates) and attributions (sentences). Some of these
systems not only provide implementable procedures for deduction but also have the advantage of being well developed and thoroughly tested. Finally, there is the apparatus of linguistics, with several syntactic categories and myriad rules of grammar.
Despite the ready availability of the foregoing concepts,
most of the work that has been done in the field of information storage, organization, and retrieval has been based on the simplest of ideas about sets. The next most popular schema, if we count implicit as well as expUcit
application, has been geometric space. We may organize
our examinations of this area, therefore, by considering storage, organization, and retrieval systems based on the following models: (1) sets and subsets, (2) space analogues, (3) functions and relations, (4) predicate calculus, and (5) other formal languages.
Systems Based on Sets and Subsets
In most systems based on the ideas of sets and subsets, the fundamental concepts are set, partition, item, name, term, prescription, storer, organizer, and retriever, and
71

INTERACTION WITH RECORDED KNOWLEDGE
the logical connectives. Although details of the concepts and the names used in referring to the concepts vary considerably from system to system, the same fundamental ideas appear repeatedly.
The items are the things to be stored and retrieved: documents, facts, and so forth. There is a set of items.
Each item may or may not have a name. Terms are
associated with items by being written, usually by storers, on the items themselves or on tags or cards associated with the items. Prescriptions are made up mainly of terms and are usually written by retrievers. For each system, there is a rule that determines whether the terms associated with a given document sufficiently match those of a given prescription. The rule and the mechanism for implementing it are devised by organizers. The object of retrieval, in systems based on sets and subsets, is to partition the set of items in such a way as to separate the items a retriever desires from those he does not desire.
In order to estabhsh a perspective, let us examine briefly, and somewhat abstractly, some familiar retrieval schemes.
Partitioning by naming
The very simplest retrieval method achieves the partition by naming the elements (or items) of the desired subset. That method is not applicable to such items as sentences and facts that do not have names. Moreover, when the retriever does not know the names of the items he desires, the method does not work even with those items that do have names, such as books and journal articles. Nevertheless, the method and the location-coded cards often used in implementing it are simple and widely
used.
72

STORAGE, ORGANIZATION, AND RETRIEVAL
Hierarchical indexing
If the items have no names, or if the names of desired items are unknown to the retriever, it is necessary to fall back on the use of descriptive terms to specify the desired items. In most term-based systems, either it is assumed that the retriever knows the terms, or glossaries or thesauri
listing the legal terms of the system are provided. In a hierarchical system, first the over-all set of items is partitioned by organizers into mutually exclusive and exhaustive first-echelon subsets or categories, and a unique term
(sometimes a code digit) is assigned to each. Then each
first-echelon subset is partitioned into mutually exclusive and exhaustive second-echelon subsets or categories, and a unique term (or code digit) is assigned to each of them. This process of subdivision is continued until there are
as many echelons as can be handled conveniently or until
there are only a few items in each subset of the lowest echelon. The retriever in this system merely composes a
prescription consisting of one term for each echelon. He makes his way down the branching, rootlike structure of
the hierarchy, selecting first the first-echelon subset corresponding to the first-echelon term of his prescription, then the second-echelon subset corresponding to the
second-echelon term of his prescription, and so forth.
When he gets to the bottom, or to a level at which there are not too many items, he examines the items of the
subset he has isolated. In practice, the main trouble with this scheme is a trouble inherent in all serial-decision methods: one mistake anywhere in the series, and the game is lost! Perhaps a more basic difficulty is that knowledge does not seem to be naturally susceptible to hierarchical analysis. For these reasons, storage and retrieval systems that set out to be hierarchical often turn into lat-
73

INTERACTION WITH RECORDED KNOWLEDGE
ticelike systems through nonexclusive categorization and
cross referencing.
Coordinate indexing
The difficulties just mentioned can be avoided by giving up the notion of precedence that orders the hierarchy. Without precedence, all the subsets and all the terms are
coordinate. In coordinate indexing systems, the organizers
partition the set of items in various premeditated ways and assign a term, not to each subset, but to each parti-
--tion. The term itself identifies one of the two subsets
separated by the partition usually the smaller one. (If negation is used, the negation of the term identifies the other subset. ) The retriever then draws up a prescription consisting of terms joined by logical connectives. Often the logical "and" is the only connective employed. In
some systems, use is made also of "or" and "not." The mechanism that fulfills the prescription has to find and de-
liver the subset of items corresponding to the logical expression. Given, for example, the prescription:
R = AV{BAC)V(DAE)
the mechanism would retrieve the items characterized by
A and those characterized by both B and C, and, in addi-
Dtion, those characterized by but not by E. Many com-
mercial and government systems are based on coordinate indexing: e.g., most edge-notched-card systems, the PeekA-Boo Card system, and the descriptor system of the De-
.
fense Documentation Center.
Inverse filing
The "natural" or "first-thought" way to set up a co-
ordinate-indexing system with cards is to assign a card to
74

STORAGE, ORGANIZATION, AND RETRIEVAL
each item and then to record the terms appHcable to the
item on the card. Second thought, however, may lead to
the opposite procedure: assign a card to each term, and record on each card the names or codes of all the items
Ato which the term applies. file organized the second
way is an "inverse" file. Its main advantage is that, since ordinarily there are more items than terms, it requires fewer cards. In the Peek-A-Boo system, each card is divided into many small areas, one for each actual or anticipated item, and an item is associated with a term by
punching out the item's area, thus leaving a hole, in the
card for the term. When the desired term cards are piled,
one on top of another, to form a deck, and are held up to the light, one sees light through the entire deck at the location for each item to which all the terms apply. This is, of course, merely one of several convenient implementations of the logical "and." It illustrates the natural congruence that exists between punched cards and Boolean algebra.
Hybrid systems
Because knowledge has a more complex structure than coordinate indexing can mirror, and still is less perfectly hierarchical than systems based on rootlike branching and exclusive categories must postulate, there have been several efforts to develop hybrid systems that would combine the advantages and avoid the disadvantages of hierarchical and coordinate indexing. One such approach is to employ only a very few echelons of hierarchy and to use coordinate indexing within each echelon. Another is to build a quasi-syntactic structure upon the coordinateindex base by assigning role indicators to the terms. One may distinguish between Ri, wax made by bees, and R2,
75

INTERACTION WITH RECORDED KNOWLEDGE
bees made of wax, for example, by establishing an ad hoc
two-echelon hierarchy: (a) product, (b) source or con-
stituent. In that case we have:
=Ri (a) wax, (b) bees =R2 (a) bees, (b) wax =Alternatively, one can define the role indicators: P = =product, S source, C constituent. In that case we
have:
=jRi wax (P), bees (5) =R2 wax (C), bees (P)
It seems unlikely, however, that such circumventions will lead to highly sophisticated or truly elegant storage and retrieval systems. The fundamental trouble seems to be that elementary set notation and Boolean algebra are inadequate to express compactly the subtle distinctions and intricate relations involved in a sophisticated representation and organization of the body of knowledge. In saying that, however, one should be sure to acknowledge that storage and retrieval systems based on sets and subsets have a particularly strong congruence with presentday information-processing technology and that, despite their limitations in sophisticated applications, they seem to be capable of achieving a high level of effectiveness in document retrieval and even in the retrieval of relevant passages within documents. That is to say, their shortcomings seem likely not to manifest themselves strongly
until an effort is made to deduce or infer consequences
from the stored representation of knowledge.
76

storage, organization, and retrieval
Space Analogues
The basic notion of topological space analogy is that one item (document, fact, or idea) is the "neighbor" of another item to which it is closely related. Metric space
analogy involves the notion of distance in addition to the
notion of neighborhood: two items may be close together or far apart, and the distance between them may
be analyzed into n components corresponding to the n dimensions of the space.
Metric space analogy is to some extent implicit in the many information-retrieval studies that have used product-moment correlation, multifactor analysis, and related "linear" methods. However, those studies have not emphasized the space concept, and they have led to httle or no consensus even about the dimensionality, much less about the identities of the dimensions, of any such thing
as "information space" or "semantic space" or "the space of knowledge."
Doubtless the most literal application of the space concept has been Osgood's "semantic differential," based
on factor analysis of many human scaling judgments relating linguistic "objects" (such as statements) to named attributive scales (Osgood, Suci, and Tannenbaum, 1957). Osgood and his colleagues have shown, for ex-
ample, that the same half-dozen basic factors appear in
almost all human judgments, and that the fundamental
--affective dimensions are almost the same the world over in 16 different ethnolinguistic contexts.* One can see
a possibility of relating Osgood's kind of semantic space to the space in which Swanson (1959) has determined
correlations among the occurrences of descriptive terms
* C. E. Osgood, Personal communication, March 1963.
77

INTERACTION WITH RECORDED KNOWLEDGE
and to the space in which Giuliano has determined correlations of the contexts in which descriptive terms oc-
cur (Giuliano and Jones, 1963; Giuliano, 1963). How-
ever, that possibility has not been developed. There has
been much use of methods that assume linearity (and in
some instances statistical independence) of the basic
variables, but not much explicit discussion of geometric
space as a milieu for the representation of knowledge or
intellectual processes.
Much of our knowledge deals with the physical world,
however, and must be indexed to the physical dimensions of space and time. Place names are in a sense merely spatial coordinates, and linguistic tense has its roots in physical time. It seems difficult, therefore, to conceive of a representation of knowledge within which a geometric
framework does not play a major role. How can the at-
tractiveness of the space analogy be reconciled with the obvious merits of logical and linguistic schemata that involve neither geometry nor continuous variables?
The most promising approach, it seems to us, is to accept the notion that, for many years at least, we shall not achieve a complete integration of knowledge, that we shall have to content ourselves with diverse partial models of the universe. It may not be elegant to base some of the models in geometry, some in logic, and others in natural language, but that may be the most practicable solution.
Functions and Relations
WilHams, Barnes, and Kuipers (1962) have described an approach to document retrieval based on analysis of natural-language expressions (such as titles) in terms of
78

STORAGE, ORGANIZATION, AND RETRIEVAL
arguments and functions. In our study, a similar approach was developed in terms of relations.
Functions and relations appear to cover very nearly
the same ground. If z is a function F of x and y, which
=we may write z RF(x,y), then there is a relation Aamong x, y, and z, and we may write it R(x, y, z).
relation may have any number of arguments. If it has one
argument, it is merely an attribute or property. It seems reasonable to say that a single relation, say, Rio{a, b, c, d, ' ' ,t), might subsume all the interactions described in a long sentence.
The following discussion involves a long example based on a sentence of medium length. The example leads to the statement of a problem and an expression of belief,
but not to a solution or a method. Earlier in this report there appears the sentence: "They
will comprise the echelons of the memory hierarchy we
have mentioned." If a procognitive system were to try
to make sense of that sentence, it would first have to de-
termine the referents of the pronouns. Let us suppose that
it is able (with or without human help) to figure out that "they" refers to computer memories that embody
various compromises between small-and-fast and largeand-slow, and that "we" refers to the participants in the study, or perhaps to the author together with the readers. The sentence then amounts to the assertion that a complex relation exists among several entities: {a) computer,
{b) the memories, (c) time, {d) the echelons, {e) mem-
ory, (/) the hierarchy, {g) the participants, {h) comprising, and (/) mentioning.
To take up the matter a small part at a time, in an intuitively guided sequence, we may note first that there
79

INTERACTION WITH RECORDED KNOWLEDGE

is a component relation that is nothing more than a
simple quahfication (of the common name) of a part of something by associating with it (the common name of)

the thing of which it is a part. Thus we have "the com-

puter memories," a relation between (a) and (b) that we may represent as Rii(a, b). In "the memory hierarchy,"

we have another qualification, but of a slightly different kind. The hierarchy is not part of the memory. Instead, the memory is part of the hierarchy, or at any rate mem-

ory is the stuff with which the hierarchical structure is

Wefilled.

may write R\2\{f, e), using the common initial

subscript to signify the similarity, the distinct second sub-

script to signify the difference, and the third subscript as

a hedge against future complications.

Next let us look at "the echelons" and "the hierarchy."

The echelons are abstract parts of the hierarchy. That relation we may call R122U, d), indicating that it is similar

to, and also that it is different from, R121U, e).
We put the verbs at the end of the list because verbs
seem so much like operators and so different from sub-

stantives. Nevertheless, let us represent the relation be-

tween "time" and "comprising" as Rz{c,h), and the

relation between "time" and "mentioning" as Ri (c, z).
We come now to larger parts of the over-all relation

of the sentence. Let us consider "the authors have mentioned," and then let us consider "the memory hierarchy

the authors have mentioned." The smaller segment is

RAg, Ri{c,i)^. The larger, which must include some equivalent to the notion that the memory hierarchy is in

the main clause whereas the rest is in a dependent clause,

IS R,{Rv2i{f,e),R,[g,R,{c,i)]}.

The complex just constructed must mesh with "the

80

STORAGE, ORGANIZATION, AND RETRIEVAL
echelons of the memory hierarchy." The two ideas have to fit together in such a way as to indicate that we are planning to move the train of thought forward with the echelons, but that we want to acknowledge that they are parts
of a hierarchy, that the nature of the stuff of which the
hierarchy is made is memory, and so forth. We may call
the abstract meshing relation, together with its nuances,
Riix, y), and we may make it specific to the sentence in
question by substituting the arguments: R-(^Ri22(f, d),
Re{RMf, e), R-.ig, R.{c, i)]})^
Finally, to wind up the example with one big step, we may express the relation among "the computer memo-
ries," "comprising" (in the future), and all the rest that
we have dealt with as: Rs \^Rii(a, b), Rz{c, h), R- (-R122
{f,d),R6{Ri2iU,e),R,[g,Ri(c,i)]})]. That formula reflects to some extent the order in which the parts were combined. Since certain other sequences of partial combination would have been equally defensible, it is clear that there are alternative formulas that are equivalent to the one developed.
Now, although the foregoing discussion is ridiculous in several ways, it is instructive in one way and challeng-
ing in another. It is ridiculous in that the relational ex-
pressions generated are complex and inscrutable, whereas the sentence itself was fairly simple and fairly clear.
Unfortunately, it is probably ridiculous also in that we
were able to set forth neither a taxonomy of relations nor an algorithm for simplifying the relational expressions. Nevertheless, the relational notation impresses us as much closer to an organizable, processible cognitive structure
than is the sentence made of words. Note how much detail there turns out to be in a 12-word sentence. The

INTERACTION WITH RECORDED KNOWLEDGE
relational notation makes the detail explicit and manipulable. It challenges us to develop taxonomies and simpli-
fication procedures.
Chomsky's (1957) concept of transformational gram-
mars offers a promising approach to both tasks. If Chom-
sky's methods were fully developed, one could transform
any grammatical sentence into canonical form. Some of the information of the original sentence would then reside
in a designation of the transformation that was apphed, and some would reside in the canonical expression that
resulted. On the average, of course, the canonical expres-
sion would be simpler and more straightforward than
the original.
Even with some of the structural linguistic information factored out, much would remain in the canonical sentence. Some of that information would reside in the syntactic structure; more of it would reside on the nonsyntactic facets of the relations among the elements. Indeed there appear to be at least some thousands of significantly different relations among things. It is not entirely clear that the number is finite, even if we make an engineering interpretation of "significantly different." However, it seems somewhere between conceivable and likely that the myriad and diverse observed relations are com-
-- --pounded of a few dozen perhaps a hundred atomic
relations, and that the great variety arises when the atoms are combined in ways reminiscent of organic chemistry.
If it should turn out to be so, then relational analysis will almost surely be a powerful technique for use in the representation and organization of knowledge.
Our initial thoughts along the line of relational analy-
sis were concerned with relational nets, an example of which is shown in Fig. 4.
82

STORAGE, ORGANIZATION, AND RETRIEVAL

Fig. 4. The diagram represents a relational network. The circles

represent entities, relations, and properties. Entities, relations, and
properties may participate in relations and have properties. The ulti-

mate property is being a property. The "input terminals" of relations are marked by black spots. Ordered terminals are identified by num-

bers. Interpretations of the diagram, such as "John and Jim are

brothers, and John is taller than Jim" and "Jack has red hair," are

Weexplained in the text.

hypothesize that, in a fully developed rele-

vance net of this kind, the alphabetic labels can be erased without
--loss of any basic knowledge of the situation represented i.e., with-

out loss of any information other than that rooted in arbitrary selec-

tion of unessential symbols.

Consider the circles labeled "John" and "Jim." That they represent individuals is indicated by their connection
--by arrows to "individual." Individualism being an in--dividual is a property, as is shown by the connection
from "individual" to "property." Being a property is also

83

INTERACTION WITH RECORDED KNOWLEDGE
a "property," as is shown by the recursive arrow. John and Jim are both male, and they are siblings, therefore brothers. "Sibling" is an /7-ar2ument relation, and being an ^-argument relation is a property. Every path ends at
"property."
There are two "sibling" circles, for one set of siblings uses up a circle, and Jack and Jill are siblings too. As is shown by the arrows from the two "siblings" to "same," being a sibling is the same as being a sibling. "Same" is an unordered, n-argument relation, and "unorderedness" and "/i-argumentness" are properties.
"Jack" and his "hair" participate in a whole-part relation and also in a possessor-possessed relation. Both relations have two ordered arguments. The hair is red.
Red is a color. Red and color are both properties. Thus
Jack has red hair. It is all extremely simple at each step,
but there seems to be room for many steps. As the number of relations and properties grows, the
lower-level labels that are not wholly arbitrary can be figured out more and more readily from the higher level labels. In a complete relational net, all the unarbitrary information resides in the structure; the labels (other than the numbers that order the arguments of orderedargument relations) are entirely superfluous. Relational nets are consequently very attractive as schemata for computer processing.
During the last few months of the library study, Marill (1963) developed the idea of relational nets in the direction of a predicate calculus (see Part II). Marill and
Raphael are now simulating net structures on a computer
and developing programs that will organize and simpHfy
nets.
84

storage, organization, and retrieval
Predicate Calculus
Much of the research during the second year of the
study was devoted to question-answering systems. The system constructed by Black, to be described briefly in Part II, was based on the representation of information in the form of statements in first-order predicate calculus. With the information in that form, and with the aid of computer programs designed to process it, the computer could deduce from its information base answers to vari-
Weous questions stated in the formalism (Black, 1963).
believe this to be a significant development. It demonstrates the advantage of employing a formalism that approaches the sophistication and complexity necessary to represent efficiently the subtleties and intricacies of thought and knowledge.
Two other researches are using predicate calculi in
ways somewhat similar to Black's. Bohnert,* of the Thomas J. Watson Research Center of I.B.M., is using the first-order predicate calculus. McCarthy,! of Stan-
ford University, is using a second-order predicate calculus
that degenerates to first order when time is held constant.
Two severe practical problems are encountered along
the path taken by predicate calculus. First, there is as yet
no way to translate automatically from statements in
natural language to statements in predicate calculus; the
translation must be made by people, few people can do it, and the process is time consuming. Second, a small amount of natural lan^ua^e turns into a lar^e amount of predicate calculus. The first problem is, of course, a basic
* H. G. Bohnert, Personal communication, November 1963. t J. McCarthy, Personal communication, November 1963.
85

INTERACTION WITH RECORDED KNOWLEDGE
research problem as well as a practical one. The second problem places its demand upon the information tech-
nology.
Higher-Order Languages
At this stage it seems to be a very good hypothesis that languages of high order are required for compact representation of knowledge, and it seems to be a fairly good
hypothesis that such languages are required for efficient
processing of knowledge. Even highly complex things can be said in very simple languages. For instance, if there were an element in a set for every possible statement, one could make any statement merely by pointing to its element. However, in low-order languages (such as the language of elements, sets, and Boolean operators) the representation of a complex molecule of knowledge is disproportionately voluminous. Our perception of this matter, though still somewhat nebulous, has led us to a rather firm conviction: that the economic and practical advantages of linguistic sophistication are great, and that
the intellectual advantage is even greater.
The conviction just set forth is coupled with a second conviction that is less firmly set but is nevertheless a working conviction: in a lansiuase to be used in procosni-
tive systems, formality is an extremely valuable asset. Both the lack of formality and the failure to adhere strictly to the rules can cause great difficulties in all kinds
of machine processing of information. The problem is not the inconvenience caused by grammatical errors or
ambiguities of vocabulary, but rather the high price that
civilization pays for the capabihty that lets man navi-
gate through his sea of syntactic sorrow and semantic
86

STORAGE, ORGANIZATION, AND RETRIEVAL
confusion. It is almost obvious that man's inability to organize the corpus of his knowledge tightly is due to his having to squander such a wealth of intellectual resource
each time he reads a paragraph. For all these reasons we
strongly favor the idea of developing high-order formal languages and applying them with machine assistance in
organizing the body of knowledge. Natural English is a high-order language, of course,
--and, when correctly written or spoken, it may even ad-
here to a definite form though surely no one knows quite what the form is. If we try to say what is wrong with English, perhaps we can sharpen the concept toward which we are pointing.
The main shortcoming of English, and presumably of any natural language, is its ambiguity. Natural languages
are so often used as adjuncts to nonlinguistic processes that natural languages do not have sufficient chance to practice independence and to develop self-sufficiency.
--Moreover, when they are exercised in isolation from non-
linguistic processes in reasoning out solutions to diffi-
--cult problems, for instance there is very little op-
portunity to track down sources of error or confusion. Thus ambiguity persists because it creates no serious
difficulty in situations in which the difficulty could be detected and corrected, and ambiguity is rarely detected in situations in which it creates great difficulty. It is no wonder, therefore, that "in" and "of" stand for twenty
different relations each, and that "When locked enter through 3D-100" does not tell you what to do when you are locked, nor does it tell you to go through room 3D-100 when the door of 3D-100 is locked.
In short, the trouble with English as a carrier of knowledge is the horrendous amount of calculating on a very
87

INTERACTION WITH RECORDED KNOWLEDGE
large base of data that is expended just to decide which of several locally plausible interpretations of a simple statement is correct or was intended. If the greater part of man's capability is wasted in that kind of processing, he does not have enough left to achieve more significant goals. This conclusion is obvious when the processing of Enghsh text is attempted by a present-day computer. It is less obvious but probably just as true for people.
The higher-order language that we propose as an effective carrier for knowledge is a kind of unambiguous English. As long as changes of context are signaled explicitly within the language, no serious problem is introduced by dependence on context. (Indeed, dependence on context appears to be necessary for the achievement of efficiency in diverse special applications.) The proposed language would recognize most or all of the operations, modulations, and quahfications that are available in English. However, it would quantize the continuous variables and associate one term or structure un-
ambiguously with each degree. Finally, the system in which the proposed language is to be implemented would enforce consistent use of names for substantives; it would
monitor "collisions" among terms, ask authors for clarifications, and disallow new or conflicting uses of estab-
lished symbols. All this advocacy of unambiguous, high-order lan-
guage may encounter the disdainful accusation, "You're
just asking for ruly English!" However, the situation is
more favorable now for a ruly version of English than it ever has been, and it will be fully ripe before the new language is likely to be developed. The situation will be ripe, not because people will be ready to adopt a new
dialect, but because computers with large data bases will
88

STORAGE, ORGANIZATION, AND RETRIEVAL
need the new dialect as an information-input language. The envisioned sequence is: from (1) the natural (tech-
nical) language of the journal article through a machineaided editorial translation into (2) unambiguous English, and then through a purely machine transformation into (3) the language (s) of the computer or of the data base itself. At any rate, this is a plausible approach that deserves investigation, though the areas discussed earlier, particularly relational nets and higher-order predicate calculi, will surely provide competitive approaches.
89

