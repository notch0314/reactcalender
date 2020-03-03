# **Introduction**

`ES6` introduced a new way of working with functions and iterators in the form of `Generators` (or generator functions).
A generator is a function that can stop midway and then continue from where it stopped. Basically, a generator appears to be
a function but it behaves like an iterator.

Here is an analogy to have an intuition for generators:

Imagine you are reading a book, and you hear someone ring your doorbell. Before you get up to open the door, you
**set a bookmark at the last page you read**. You mentally saved the events of the book and got up to open the door.
Once you return and go back to reading your book, you **start from the page that you set your bookmark on** and not from
the first page again. In a sense, you acted as a **generator function**.

