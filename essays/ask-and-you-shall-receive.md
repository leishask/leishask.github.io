---
layout: essay
type: essay
title: Ask and You Shall Receive
# All dates must be YYYY-MM-DD format!
date: 2018-09-06
labels:
  - Software Engineering
  - Communication Skills
  - Open Source
  - Asking Smart Questions
---

## Put Your Mind to Work
Have you ever asked a question and received a wise remark instead of an answer? This could have been the result of you being uninformed of how to correctly ask well-developed questions that evoke useful answers, or an answer period. I witness students every day ask "bad questions" that could be answered by simply referring to the syllabus. Why would someone repeat information that has been discussed and is easily accessible? 

Always research and look through resources to find a solution to your problem or concern before consulting an expert. This will show that you made an effort. Plus, you may even find the answer to your question. The world is at our fingertips, yet we waste valuable time asking bad questions. When we start asking smarter questions that are thought-out, straightforward and clear, we can further our horizons.

## Bad Questions are a Thing of the Past
Browsing through Stack Overflow, a question and answer site, I came across a good example of a bad question. This very question was actually declared "closed" by several users because it was so poorly executed that it was deemed useless to others.

In the following example, a user asks how to replace '>' with '>\n' in a java code.

```
Q: Can anybody help me in replacing '>' with '>\n' inside string in java?

Can anybody help me in replacing > with >\n inside string in java?

For example:

String str = "abc>";
str = str.replace(">",">\n");
```

First off, the user's question is asking if someone will help them. Yet it is unclear what exactly the user is having a problem with. It seems that they are looking to debug the code without providing the specific error they are receiving. With a little more clarification and better rewording, the user could easily turn this question into a question that yields useful results.

## Solving Solutions with Smart Questions
If you want real answers, you have to ask smarter, detailed and concise questions. To avoid other users from voting your question to be closed, the following example will illustrate a question that will deliver beneficial answers.

```
Q: Why is S::x not odr-used?

Consider this example from cppreference:

struct S { static const int x = 1; };
void f() { &S::x; } // discarded-value expression does not odr-use S::x

I agree that &S::x is a discarded-value expression, since the standard says (9.2, paragraph 1 [stmt.expr] from n4700)

    Expression statements have the form

    expression-statement:
        expression_opt ;

    The expression is a discarded-value expression (Clause 8)...

However, is that enough for S::x to not be odr-used? 6.2, paragraph 3 [basic.def.odr] states

    A variable x whose name appears as a potentially-evaluated expression ex is odr-used by ex unless

        ...
        if x is an object, ex is an element of the set of potential results of an expression e, where either
            the lvalue-to-rvalue conversion (7.1) is applied to e, or
            e is a discarded-value expression (Clause 8).

The problem is that the discarded-value expression &S::x has no potential results (which means that S::x is not a potential result of &S::x), as you can see from 6.2, paragraph 2 [basic.def.odr]:

    ... The set of potential results of an expression e is defined as follows:

        If e is an id-expression (8.1.4), the set contains only e.
        If e is a subscripting operation (8.2.1) with an array operand, the set contains the potential results of that operand.
        ...
        Otherwise, the set is empty.

Then, how can you explain that S::x is not odr-used?
```
