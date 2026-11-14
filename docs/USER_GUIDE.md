# Pomly User Guide

Pomly has three sections in the bottom navigation: Focus, Cards, and Streak.

## Focus Timer

1. Open **Focus** and use the timer controls to start, pause, or skip the current interval.
2. Open **Timer settings** to set focus time from 1 to 120 minutes and break time from 1 to 60 minutes.
3. A completed focus interval starts a regular break. After five completed focus intervals, the next break is five times the configured break duration.
4. When the long break ends, the timer returns to a ready focus interval. Start it when you are ready to continue.

Focus time is recorded as the timer runs. Timer settings and study history are stored locally.

## Create and Review Flashcards

Open **Cards** to paste notes or import a selectable-text PDF. Set the card target before parsing; the screen supports targets from 30 to 70 cards. Each successful import creates its own deck.

Text imports support explicit pairs such as:

```text
Q: What is a closure? A: A function with lexical scope

Q: What is a widget?
A: A reusable user-interface element

term :: definition
front -> back
```

The local parser can also generate cards from supported definition-style prose and study sentences. Its results are heuristic, so review generated prompts and answers before studying. It does not use a cloud AI service.

PDF import extracts selectable text from up to the first five pages. Image-only scans generally cannot be parsed. The original PDF is not uploaded; extraction happens on-device.

Choose a deck to review its due cards. Reveal each answer, then rate recall:

- **Again** schedules the card again soon.
- **Hard**, **Good**, and **Easy** schedule progressively longer review intervals.

Use the edit control to adjust a card. Deleting a deck removes that deck and its cards from local storage.

## Tasks, Goals, and Streaks

Open **Streak** to add and complete daily study tasks, review logged activity, and adjust weekly study-minute and task goals. Focus time, card reviews, and task activity contribute to the shared activity history.

A study activity keeps the current rhythm active and restores the rest allowance. You can log a named rest day for recovery, travel, exams, or health. Up to three consecutive unexplained quiet days are covered by the rest allowance; after it is exhausted, the streak resets. A logged rest day preserves the rhythm while consuming allowance.

## Local Data

Pomly stores settings, decks, cards, tasks, and study history on the device using application preferences. There is no account, sync service, or web dashboard. Data is not automatically transferred between devices.
