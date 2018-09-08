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

<img class="ui medium right floated image" src="../images/stupidQuestions.jpg">

## STFW and RTFM
Have you ever asked a question and received a wise remark instead of an answer? This could have been the result of you being uninformed of how to correctly ask well-developed questions that evoke useful answers, or an answer period. I witness students every day ask "bad questions" that could be answered by simply referring to the syllabus. Why would someone repeat information that has been discussed and is easily accessible? 

Always research and look through resources to find a solution to your problem or concern before consulting an expert. This will show that you made an effort. Plus, you may even find the answer to your question. The world is at our fingertips, yet we waste valuable time asking bad questions. When we start asking smarter questions that are thought-out, straightforward and clear, we can further our understanding.

## What do you even mean?
Browsing through Stack Overflow, a question and answer site, I came across a good example of a bad question. This very question was actually declared "closed" by several users because it was so poorly executed that it was deemed useless to others. You cannot expect someone to answer a question that they do not understand.

In the following example, a user asks how to replace '>' with '>\n' in a java code. The question itself can be interpreted in numerous ways.

```
Q: Can anybody help me in replacing '>' with '>\n' inside string in java?

Can anybody help me in replacing > with >\n inside string in java?

For example:

String str = "abc>";
str = str.replace(">",">\n");
```

First off, the user's question is asking if someone will help them and yet it is unclear what exactly the problem is. It seems that they are looking to debug the code. However, they did not provide the specific error they are receiving or output they are expecting. With a little more clarification and better rewording, the user could easily turn this unfit question into a question that yields useful results for everyone.

## Give me the details
If you want real answers, you have to ask smarter, detailed and concise questions. To avoid other users from voting your question to be closed, the following example will demonstrate a question that has delivered beneficial answers.

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

While everything can be improved somehow, the above question is clear with evidence of prior research. For this example, the user is looking for clarification about a possible inaccuracy in C++. The user provided details and facts to back up their concern. Which shows that the user researched an explanation before consulting the Stack Overflow community. In return, the user received a detailed explanation to the question as well as invoking other users to discuss the topic further. Isn't that really what asking questions are about? Furthering the knowledge of yourself and others?

## Now you know
Asking a question can be either beneficial or useless depending on how you ask, not just what you ask. If you ask a question that is vague and self-serving, you will most likely receive an answer that is unfavorable to you, maybe even no answer at all. People take the time out of their lives to answer questions that can benefit more than just one person, especially if the answer cannot be found anywhere else.

Next time you ask a question, ask a smart question. Remember to do your research first, be courteous, be concise, and be considerate.

You can check out the examples from Stack Overflow here: [Bad Example](https://stackoverflow.com/questions/44687017/can-anybody-help-me-in-replacing-with-n-inside-string-in-java) and [Good Example](https://stackoverflow.com/questions/47952024/why-is-sx-not-odr-used)
