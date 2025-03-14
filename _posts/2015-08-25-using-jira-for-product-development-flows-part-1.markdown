---
# layout: post
title: "Using JIRA for Product Development Cycles part 1"
date: 2015-08-25 00:01
comments: true
feature-img: "assets/img/jira/jira-logo.png"
thumbnail: "assets/thumbnails/jira.png"
categories: [product management]
---
[JIRA](https://www.atlassian.com/software/jira) is a popular tool for managing software product projects. In my role as Product I've been an active user of this tool as well as [Trello](https://trello.com/), [Pivotal Tracker](https://www.pivotaltracker.com/) among others in the last few years and, have found different ways that these tools can be used for organizing our product development cycles.

The tools are only the channel used by the organization to have a central location where the engineering teams tracks product implementation tasks, level of effort, bugs and, escalations. At the same time, the Product team uses the tools to communicate current features that are implemented, prioritize new features, plan out new releases and even define product roadmaps.

But as with any tool, if you don't proactively maintain the information, it quickly becomes outdated and easily forgotten. In this article I would like to describe how I've use JIRA as a Product within the software development lifecycle.
<!--more-->

## JIRA Projects

We created multiple JIRA projects for our product development that serve as layers or filters in which we would catalog all the different asks for the engineering team: from feature requests, to escalations, to bug fixes. We quickly understood that in order to maintain an organized engineering backlog, we needed to protected it at all cost.

For that, the engineering leaders and product team took the responsibility to manage the following buckets as described below:

### Feature Requests - FR
**Owner:** Product team

**Purpose**: The bucket where the product team receives and manages feature requests, enhancements, documentation issues, etc. After the product team evaluated and defined how to best address a given feature requests. We would either approve the feature request via a story or set of stories that go in the icebox or, we would decline the feature request.
Although we used JIRA,  in reality this project could be managed with a simpler and more friendly tool like Trello. You can get created and use tools that are easy to use by all the parts of the organization.

### Icebox - IB
**Owner:** Product/Engineering

**Purpose:** This project was used as a [agile Kanban](https://www.atlassian.com/agile/kanban) board. Here,  product and engineering would place upcoming engineering work. Prior to sprint planning, each team made sure that the most important stories based on eachother's priorities where registered and presented during sprint planning meeting. We had a dedicated column called (next sprint). Once the sprint backlog was defined we move all stories for the new sprint into the **Active Sprint** project.

### Active Sprint - AS
**Owner:** Product/Engineering

**Purpose:**  This project can be setup either as a [Scrum board](https://www.atlassian.com/agile/scrum) or a Kanban board. It contains the engineering tasks for the current sprint. The team worked to have real expectations and whatever was in the sprint would gotten finished on the sprint. This particularly is a great exercise to keep a good team morale.

### Escalations - ESC
**Owner:** Product/Engineering leads

**Purpose:** The engineering team's window to the outside world. A project used by everyone in the organization to register things that were "urgent" or that required attention from engineering. The product team and engineering leaders would triage the issues and requests.
As part of the triage the owner would either gather more information, or create an escalation that could go directly into the current sprint (AS project) to be addressed immediately or go into the icebox (IB) to be consider for a future sprint.


### Final Remarks
Remember that JIRA allows you to do bulk changes, which come really handy when moving things from project to project. Also, keep common guidelines that help to maintain consistency across multiple JIRA projects. For example: same components set, common labels, notation, etc.

And last but not least, **purge your icebox** often. It's super easy to put things in but really hard to get them out. At the end everything will look as it's important.
