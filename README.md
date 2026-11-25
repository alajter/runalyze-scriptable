# Runalyze widget for iOS

My Runalyze numbers on the iPhone home screen, without opening the app.

<img src="https://user-images.githubusercontent.com/45463445/195308981-7a57c321-19df-4561-be44-423db451da6e.png" alt="light mode" width="300"/>
<img src="https://user-images.githubusercontent.com/45463445/195309708-cc70e2e5-60b4-468b-8349-aaa19ac0b968.png" alt="dark mode" width="300"/>

## The problem

[Runalyze](https://runalyze.com) calculates useful numbers from every run: effective VO2max, marathon shape, fitness and fatigue, the workload ratio, recommended rest days. To see them I had to open the website and look for them. I wanted the four I check most on my home screen.

## Who it is for

Me, and any Runalyze user with an iPhone who is happy to paste a script into [Scriptable](https://scriptable.app).

## What it does

A Scriptable widget that signs in to Runalyze, reads the calculations panel and shows:

- effective VO2max
- recommended rest days
- marathon shape
- stress balance (TSB)

It follows the phone's light or dark mode.

## Decisions

- **No app to build.** Scriptable runs JavaScript widgets on iOS, so this is one file.
- **Reads the page.** The script signs in and reads the same calculations panel the website shows. It breaks if Runalyze changes that page.

## Set it up

1. You need a [Runalyze](https://runalyze.com/) account and [Scriptable](https://scriptable.app) on your iPhone.
2. In Scriptable, tap **+**, paste the contents of `Runalyze.js` and name the script `Runalyze`.
3. Add a Scriptable widget to your home screen ([how](https://support.apple.com/en-gb/HT207122)).
4. Edit the widget: pick the `Runalyze` script and set **Parameter** to `username#password`.

The first sign-in can take a while. If the widget stays empty, run it again after a minute. The app and the widget use separate sessions.

To show other values, change which entries of the calculations panel are read (around lines 73 to 96 of `Runalyze.js`).

Provided as is, for personal use.

## The series

Four attempts at the same question for the same runner (me): what should I run today, and is the plan still right?

1. [runalyze-scriptable](https://github.com/Andrel666/runalyze-scriptable) (2022). An iOS home-screen widget with my Runalyze numbers.
2. [run-radar](https://github.com/Andrel666/run-radar) (Nov 2025 to Jan 2026). Run analytics plus sleep, and a morning readiness score.
3. [run-coach](https://github.com/Andrel666/run-coach) (Mar 2026). A broad AI coach: chat, generated plans, recovery from Apple Health, gait analysis from video.
4. [run-planner](https://github.com/Andrel666/run-planner) (Nov 2026). Narrowed to one runner and one race, with plan rules you can read and test instead of AI.
