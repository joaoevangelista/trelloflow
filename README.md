# Trello Flow
## To implement Scrum like management

Why Trello?
---

Trello is simple, beautiful highly customizable and **free for private projects** as the most important feature to me to choose over others.

 Tree view
---
  - Team
    - Ideas
      - Lists
        - New
        - Approved
        - To be Discussed
        - Junk Box
        - Not now
    - Issues Board
        - Lists
          - New Issues
          - Triage
          - Ready to group
    - Development Board
      - Lists
        - Backlog
        - To Plan
        - Current Sprint
        - In Progress (Histories with tasks in progress)
        - Done and Waiting to Release (All work that have been done on the Sprint that will be launched on the end)
        - Reiterate (Work not concluded by some reason that will need to be specified on the description, from here at the end of Sprint the card will be placed at To Plan List)
        - Release X.x.x (List to track about change logs and user histories done to track progress) (on demand creation)


# Development Board

Backlog
---

Each card representing a user history, simple as that.

To Plan
---

Histories that will be iterated on the next sprint.
Here it is the time to write down the tasks as checklists, as well acceptance criteria can be defined as checklists too
manage notes split tasks into cards if it is too complex,
on the beginning of Sprint, this list is expected to be empty

Current Sprint
---
This list is intent to be used by cards that describe the user history and
It's tasks, with additional task cards originally from user history ones.
It is wise to add to the title of the list to match the period of the sprint.

**Topic on meetings**
**Tip:**  Use a label to identify user histories among normal cards.


In Progress
---

Tasks and histories currently being working on.
Where the team can discuss implementations and technical stuff
**Topic on meetings**

Done Waiting for Release
---

When a task or a history is completed and acceptable the card must be moved to here, then it will be Waiting for the  next iteration of the release process.

Release
---

This list is an on-demand list when the sprint is completed, the cards from *Done, Waiting for Release* gets moved from there to here, declaring that a new release cycle was completed. **Tip::** Assign a version for each release or a code name, anything that can be distinguished among the other releases do you can easily create a changelog.

#Issues Board

This board is intended to be a first-heaven of issues where they will be
reported, analyzed and sent to the backlog when it is time.

New Issues
---

Here the reported issues during development or by users can get their attention from the team. New ones are placed here as a "backlog".

Triage
---

Here the team discusses the issue what it is causing and what can be done, all is written down, so if another person gets their hands on they will know what is all about.

Ready to group
---

After triage, the issues come to here to be added to the backlog on the next iteration



# Integration
## GitHub

Integrating with GitHub can be a little tricky, to manage user posted issues and comments there. For this, a managed to come up with this.

For each milestone you will support your development cycle create a list for it, take it as an "Issue Backlog for x.x.x" each card there will be a copy of the issue on GitHub, for that we can use WebHooks, upon the creation of the card a label without color can be assigned to represent GitHub issues, let's call it "GitHub", while it is creating the card if the issue as a milestone assigned to it, the bot can try to put it on a list with the version on the name. When the issue gets closed on GitHub the card is moved to the *Done* list, this can be tracked down with a simple database on in-memory map (cardId-IssueID)
**But beware, you will need to control over the version, so no one will assign a version on an already released version.**
