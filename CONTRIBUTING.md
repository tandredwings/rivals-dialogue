# Contributing to Night City Rivals: Dialogue

Thanks for wanting to write for Night City Rivals! Every line in this repo ends up as a text message a rival sends V in game, so new lines, replies and whole personalities all make the mod better.

Read the [README](README.md) first. It explains how the files are laid out, how dialogue trees work, and which `{substitutions}` you can use. Lines that don't follow it can't be imported into the game.

## How to add lines

### Small changes, right on GitHub

1. Open the file you want to add to, for example `yapper/ambush-v.md`.
2. Click the pencil icon. GitHub makes your own copy (a fork) for you.
3. Add your lines under the right gang heading: `## Generic` for any gang, or a gang's own heading for lines only that gang would say.
4. Click **Commit changes**, then **Propose changes**, then **Create pull request**.
5. In the pull request, say what you added and anything I should know.

### Bigger changes

Fork the repo, make your changes on a branch, and open a pull request. Keep one pull request to one personality or one event where you can. Small pull requests get reviewed faster.

## What makes a good line

- **Say what happened.** V should be able to tell who's texting and why. "Coming for you." on its own isn't enough; "Got your trace, V. Me and the crew are rolling." is.
- **Fit the personality.** Each personality's `description.md` says how they text. A Laconic rival never sends a paragraph, and a Yapper never sends one word.
- **Sound like Night City.** Use the world's slang (choom, gonk, eddies, chrome, preem, delta) and keep it about the gangs, fixers and streets of the game. No real-world brands, politics or memes.
- **Keep it a text.** One to three sentences for most personalities. Use a double text (an indented line, see the README) instead of one long message.
- **Only use the substitutions in the README,** spelled exactly as listed. Anything else shows up in game as typed, braces and all.
- **Give V's replies a reason to exist.** A reply that changes something (`[personal]`, a skill check) should get V something different. A reply that only gets an insult back is fine, but don't add five of them.
- **Skill checks should pay off.** If a reply needs `[Cool 9]`, the rival's answer should be worth the build: they back down, let something slip, or call it off.

## What won't be merged

- Slurs, hate speech, or lines that target real groups of people.
- Sexual content involving minors, or sexual content in general beyond what the base game has.
- Real people, real brands, or lines copied from other games, films or books.

I may also ask for changes, or edit lines lightly for tone and length before merging.

## New personalities

Open an issue first describing the personality: how they text, and a few example lines. Once we agree it fits:

1. Copy the `template` folder and name it after the personality, in lowercase (for example `drunk`).
2. Fill in `description.md`: what they're like and how they text.
3. Write lines for at least `ambush-v`, `v-evade` and `survive-v`, so the new personality isn't silent most of the time.

## New events

Events need game code to trigger them, so please open an issue instead of adding a new event file. Describe what happens in game and when the rival would text. If it's added, I'll make the template file and you can fill it in.

## Permission

By opening a pull request, you agree that your lines can be used in Night City Rivals and distributed with it, including on Nexus Mods, and edited for the game.

## Credit

Everyone whose lines are merged is listed in `CONTRIBUTORS.md` and in the credits on the mod page. Add your name, or the handle you want to be credited as, in your pull request.

## After you open a pull request

I review every pull request. I might suggest changes, and once it's merged your lines ship with the next release of the mod.
