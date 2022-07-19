# russ_cox_regexp

Russ Cox wrote a wonderful series of articles Implementing Regular Expressions between 2007-2012 available at https://swtch.com/~rsc/regexp. The first articles point out a critical flaw in some of the most popular regular expression engines of the era that were based on backtracking. Russ contrasts the standard backtracking designs with algorithms based on finite automata. He implements versions of these differing designs, some combining multiple approaches.

There are links to source code throughout the articles and on the home page. But the sources are plain files in the webpage directory and not easy to browse or discover.

I've collected the files here for easier access.

- [**`dfa0.c`**](dfa0.c) - Generates and runs DFA states on the fly for corresponding states of NFA of regular expression. Caches DFA states as optimization

- [**`dfa1.c`**](dfa1.c) - Limits cache entries of DFA states from `dfa0.c` to bound memory use

- [**`nfa.c`**](nfa.c) - Implements Ken Thompson's algorithm to generate and run NFA for regular expression

- [**`nfa-perl.y`**](nfa-perl.y) - NFA-based regex engine with group captures that follow Perl behavior. Program has yacc parser for regex

- [**`nfa-posix.y`**](nfa-posix.y) - NFA-based regex engine with group captures that follow Posix behavior. Program has yacc parser for regex

- [**`regexp-bytecode.c`**](regexp-bytecode.c) - NFA represented as bytecode instructions for a virtual machine

- [**`regexp-x86.c`**](regexp-x86.c) - NFA represented as x86 instructions

- [**`ibm-7094.html`**](ibm-7094.html) - Description and instructions of IBM 7094 architecture

- [**`LICENSE`**](LICENSE) - MIT License

- [**`timing/`**](timing) - scripts to measure performance of different regex engines
