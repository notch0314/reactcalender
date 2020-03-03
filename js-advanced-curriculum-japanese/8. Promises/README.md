# **Introduction**

The ECMA committee defines a promise as:

> A Promise is an object that is used as a placeholder for the eventual results of a deferred (and possibly asynchronous)
> computation

Simply, a promise is a container for a future value. It allows you to associate handlers with an asynchronous action's
eventual success value or failure reason.

A Promise is in one of the following states:

- pending: initial state
- fulfilled: the operation completed successfully
- rejected: the operation failed

