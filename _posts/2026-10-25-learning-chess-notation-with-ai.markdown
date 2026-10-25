---
layout: post
title: "Learning Chess Notation with AI"
date: 2026-10-25
categories: ai chess teaching
---

I am a casual amateur chess player and have been for the past few years.
Some time ago, I bought [Marc Esserman's book "Mayhem in the Morra!"](https://forwardchess.com/product/mayhem-in-the-morra){:target="\_blank" rel="noopener noreferrer"} because I was intrigued by the sharpness of the Smith-Morra gambit and that it was also sound in higher ELO, as Daniel Naroditsky displayed many times in his speedrun videos, for example [in this one](https://www.youtube.com/watch?v=7ntWn4K1_E4){:target="\_blank" rel="noopener noreferrer"}.

I can read chess notation and think it is quite intuitive to learn but I cannot really "speak" it.
Already in the Introduction chapter of the book I read "5. Nf3, 6.Bc4, 7.0-0, 8.Qe2, 9.Rfd1" in a longer paragraph and I have a hard time visualizing the resulting position on the board in my head.
I know exactly what all the moves mean and could make them on a chessboard in front of me but doing this for every combination of moves in the book (and there are many) simply is not practical.

**I need to get more fluent comprehending chess notation to get value out of the book and I know that this is achievable with practice.**

As a quick check, I asked Gemini how I could improve my visualization skills and unsurprisingly, the AI responded with a practice routine.
But it was also able to provide me with a small interactive training application, which I thought was very cool.

A few days later, I stumbled (again I have to say) over [Matt Pococks video about his "teach" skill for AI agents](https://www.youtube.com/watch?v=s5T5oQJcJ6U){:target="\_blank" rel="noopener noreferrer"} and I thought that testing his skill to see how the AI would teach me board visualization would be very interesting.
_So, let's do it._

### Setup

The only thing we need for this to work is an empty directory in which we install the skill.
So, I followed the installation instructions with `npx` that I found in the [GitHub Repo](https://github.com/mattpocock/skills){:target="\_blank" rel="noopener noreferrer"}.
I am using Claude Code.

Installing the skills simply creates one directory for each skill, which holds a bunch of `.md` files.
There is a central `SKILL.md` file that defines some metadata at the top and then goes on to describe what the skill should be able to do in natural language.
The definition of the "teach" skill is quite big and broken up into multiple markdown files, one describes how to document the "mission statement" of the learning path for example.

The skill is invoked in the Claude CLI by typing `/teach <what you want to learn>`.
My prompt was:

> `/teach I would like to become more fluent with chess notation. I can parse and understand the moves but I have a hard time visualizing them without a chessboard at hand. The goal is to read a chess book like "Mayhem in the Morra" more or less fluently without constantly needing a chessboard for support`

After firing the prompt, the AI asked me some questions about my current chess level/ELO rating, a quick test on my visualization skills at the current moment ("Without looking at a board: what colour is the square f6, and can you name the squares on the diagonal from b1 to h7 quickly?"), and how much time I would like to spend per learning session (short daily drills vs. a few focused sessions per week vs. long deep session).

### Learning

After the questions were answered, the AI got going, and as a first step spent a little bit of time on web research to gather a selection of trusted sources.
It then wrote a mission statement in `MISSION.md`, notes about my current status in `NOTES.md`, and most importantly, created a folder `lessons/` which held an HTML file for my first lesson.
Because lessons are simply HTML files, we have the complete power of the browser available for styling content, showing images and videos, and most importantly, interactive drills.

Here is what the top of the first lesson looked like:

![the first few paragraphs of my first lesson](/assets/first-chess-notation-lesson.png){:style="width: 75%; display: block; margin: 0 auto" }

And here is the proposed curriculum for my learning journey.
It was revised and updated once new evidence of my learning progress came in.

1. Square colours + the main diagonals (geometry foundation) ← lesson 0001
2. Knight geometry: colour switching, knight targets from a square, Nc3–d5 / Nf3–g5 patterns ← next (diagonal lesson dropped: diagonals already easy, see LR-0002)
3. The opening position from memory: where every piece starts; "what changed?" quizzes
4. Morra main line in your head move by move (through move 9–10), with "where is X?" checks
5. Tracking captures and recaptures (the hardest part of following a line)
6. Following a sideline from a diagram: visualize, then reveal
7. Reading real Esserman passages

I reported any progress or difficulties during my learning journey to the AI which created markdown files in a `learning-records` folder to summarize my feedback.
In any new agent session, I needed to make sure that I used the `/teach` command again with my feedback.

I plan to come back after a few weeks and extend this post with my experience and progress, see you then!
