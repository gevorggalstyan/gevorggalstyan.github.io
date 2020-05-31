---
layout: post
title: "7 Tips for More Effective Code Reviews"
---

## 1. Treat code reviews seriously and understand their purpose

- Remember, it's not just a check for typos and spelling mistakes...
- Carry out code reviews (“pull requests”, or “peer reviews”) at the start of the integration process.
- If code to be reviewed is too big, ask the creator to divide it into smaller manageable chunks...(it shouldn’t be too long in the first place).
- Take your time and don’t rush - it’s not a task to be ticked off your to-do list, but a team effort to improve the solution quality.

## 2. Ensure reviewer(s) knows enough about the project or feature to perform an effective review

- To get a valuable review or perform an effective one, be aware of as much as possible; from how the application is built, to the architecture used.
- Comment, or receive comments, with the bigger picture in mind. It’s impossible to approve coding parts without knowing or seeing the bigger picture.
- Prepare for the review. If you’re the author, describe what you’ve done and why you’ve done it. Pro-tip: Paste a link to the task card from your task management software or have a quick meeting to explain.

## 3. Don’t be afraid to judge or be judged. It’s not a battle about who can “do it better”

- Be honest as a reviewer or a creator, don’t be afraid to disagree. The idea is to help make the code and application better.
- You’re on the same team! Encourage each other and head for the same goal.
- Respect other people's opinions. If you don’t agree, why not find a way to compromise?
- Understand that everyone has their own style and vision. Seek to understand things that you don’t. :)

## 4. Initiate discussions

- Expand on your comments. If you spot something a little “off” or you see something being approached in a strange way, try to contribute something a little more than “change this” or “replace that”.
- “Why?”, is a great question for reviewers to ask so that the reasoning or motives behind the code can be explained. Ask it regularly to help both sides learn.
- Respond to your review. If you’re the author of the code, take the time to answer each question even when you don’t agree, as they’ve taken the time to review your work with that shared goal in mind. Plus, it’s just a nice thing to do. :)

## 5. Be consistent

- Work with your team to document company best practices that you can use as guidelines for spotting mistakes in your code reviews. Discuss some standard solutions or approaches you'd prefer when it comes to the specific areas of your expertise, and go from there...
- Organize or take part in internal demos of the latest procedures to ensure that other teams are always aware of the above aspects and knowledge is continuously exchanged!
- Flag wider issues to your team to reduce the probability of making the same mistakes more than once.
- Use tools to help you maintain consistency across your projects; Roslyn Analysers/FxCopAnalyzer, StyleCopAnalyzers are good examples of external tools to validate and perform static code analysis for you...(more useful tools in point 7 below).
- Share and highlight good work to show your colleagues you appreciate what they do. Good people make work good!

## 6. Respect your team members' time

- Be sensible and pragmatic. If you're only making tiny changes, or you’re 100% confident in what you've done, don't wait or even ask for a code review if it means holding up a deployment or testing phase of the project.
- Establish some team rules. Let's say you have the “green light”, (an approval from two members for example), merge your changes. Find something that works for you and your team with all of the above and below points in mind.
- Chase people to perform reviews. It’s best not to assume that because there are no comments, you’re good to go. ;)
- Use tools to help you with the above. A nice addition is Pull Reminders for Slack which allows you to notify and remind others when they are assigned to a specific review.

## 7. Automate everything where possible

- If you don’t want to waste time on trivial stuff, spend some time and invest in static code analysis - there are some great tools (free and commercial) like SonarQube, SonarSource and NDepend, which can be integrated with your source control system, E.g. Github, CI/CD Pipeline or Azure DevOps.
- Set out your initial standards for the review using tools. If you want to ensure that standards are clarified before the review is submitted, Roslyn Analysers, StyleCop and Resharper are great to highlight the potential issues you can reference to keep standards from the beginning!
- Establish the process and follow it. For example, automate warnings instead of just breaking builds...there might be situations where things are done for a reason.
- Use automation to focus on the bigger picture and the “real” issues instead of fighting about who can find more typos or spelling errors!

## Bonus\* - Appreciate good code reviews and good code

- Be sure your team knows about good and outstanding performances with code reviews. Highlight them to motivate others to do the same and increase team quality in general!
- Share your tips (maybe you can write a blog ;)) to help others improve their practices around this - and other topics!
