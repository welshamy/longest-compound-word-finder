 Longest Compound Word Finder
=============================

Wesam Elshamy

April 13, 2013

The problem
-----------
A sequence of dictionary words, one per line, is fed to your program's standard input.  Find the longest compound word in this list.  That is, find the longest word in this list that is a concatenation of two or more words also in this list.  A word's length is equal to its number of characters.

This was a problem I was given as a test for a machine learning scientist programming job.

My solution
------------
First, sort all the words given through the standard input in ascending order in terms of their length.  I did that using a `TreeMap` with a custom `Comparator` to sort the keys based on their length.

Second, remove the longest word from the sorted list of words.  Find the shortest prefix of this word that is a compound word.  If such one exists, find out if the remainder of the word is a compound word also.  If so, then this word is the longest compound word, otherwise, repeat this step.

How to run?
-----------

1- Create a text file to use as your dictionary with one word per line.  If you are running Linux, you can use one of the dictionary files provided by the OS under `/usr/share/dict/`.

2- Compile the code:

    $ javac CompoundWordFinder.java

3- `cat` the file and pipe it to your running program:

    $ cat /usr/share/dict/words | java CompoundWordFinder

In the dictionary provided by my OS, the longest compound word is `electroencephalograph's`.  You may get a different result if you use a different dictionary.

