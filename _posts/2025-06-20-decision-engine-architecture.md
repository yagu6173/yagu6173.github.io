---
layout: post
title: "Decision Engine Architecture"
author: "Yan Gu"
categories: journal
tags: [documentation,sample]
image: spools.jpg
---

## What tasks a decision engine performs

A decision engine executes bussiness logic defined as rules. It helps with decision making of fraud risk detection and prevension. It can support both real-time decision or batched decision making. These rules needs to be pre-defined and stored in a repo that's connected to the core engine.

## End-to-end Diagram
The diagram below shows the critical components in a decision engine and how they interacts with each other in order to make rule-based decision making. 
![Copy of EDP diagram](https://github.com/user-attachments/assets/b11d3d75-e80f-432c-8a89-89b8771a700d)


## Description of each components


- Decision Editor
  It's a user-facing component for rule authors to create, edit and publish the rules.
  Publish updates the production rules with the latest version rules on rule repo

- Execution Engine xPert
  This is the core of the decision engine. It execute the rules set by the rule author once it's triggered.

- Decision workflow
  This streamslines each stages and steps in the execution of all rules on a checkpoint.
  A checkpoint is an instance of a specific decision flow and is usually associated with a use case scenario. 

- RAF
  This is the action framework that enables the determined action to be execution by downstream applications.
  Actions are configured on RAF ui


- Variable Hub
  This is where all data as variables are stored to support rule execution. There's a big data processing platform behind it.
  There are multiple types of variables such as near-real time aggregation variable, look up variable and vendor data   variables.  
  
  
- FDS
  This component is for action stack ranking:
  User-facing actions are primary. There's only one final primary action.
  Non user-facing actions are secondary. There can be multiple secondary action to execute.


