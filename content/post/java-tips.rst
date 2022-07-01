Java Tips
=========

.. lang: en

.. tags: java

Hello! Today I'm going to write about Java. You probably know that I code in Java, however, I haven't wrote about it yet. Until now. And I want to start with the right foot, which means, start with something easy to follow, and better, to put in practice.

Like the title says, I want to give you some tips about coding. Notice that some tips might apply for another languages. So, let's get started!

.. read_more

Avoiding NullPointerException
-----------------------------

I know, this exception is one of the most known, but also is an easy one to avoid. In some cases, all you need to do is change your test case, putting the possible nullable variable after. Consider this situation:

.. sourcecode:: java

 String status = myService.findStatus();

Here's a possible NullPointerException, in case of not testing the received status variable, of course:

.. sourcecode:: java

 if (status.equals("MyStatus")) {
     myService.doSomething();
 } else {
     myService.doSomethingElse();
 }

But all we need to do is:

.. sourcecode:: java

 if ("MyStatus".equals(status)) {
     myService.doSomething();
 } else {
     myService.doSomethingElse();
 }

This way we have the exact same condition and we're avoiding the exception! Very simple.

Abstracting values test cases
-----------------------------

This is a great tip, in short the idea is to abstract test cases in order to read the code easily. For example, is very common to test if some variable is null and has value. Maybe this sounds very simple to you, but trust me, at the end of the day, less is much much more.

Consider this situation:

.. sourcecode:: java

 String status = myService.findStatus();

 if (status != null && !status.isEmpty()) {
     /* ... code here ... */
 }

As I said, at the first look, seems to be nothing much, but we can do better. Like:

.. sourcecode:: java
 
 if (ValueUtils.hasValue(status)) {
     /* ... code here ... */
 }

Now take a look at these two examples above, which are very simple, but think about some bigger cases, and how uggly things can get. The code is way more readable, don't you think? By the say, a ValueUtils class would look like this:

.. sourcecode:: java

 public class ValueUtils {
     public static boolean hasValue(Object value) {
         if (value == null) {
             return false;
         }

         if (value instanceof String) {
             return !String.valueOf(value).trim().isEmpty();
         }

         /* another types and classes here ... */
     }
 }

Well guys, that's it for today. As soon as I get more tips, I'll be back! If you have any question or tip, please, share with me at the comments! o/

[`Ver em Português (br)`_]

.. _`Ver em Português (br)`: /post/dicas-java
