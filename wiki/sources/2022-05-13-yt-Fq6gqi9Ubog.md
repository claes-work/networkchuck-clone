---
type: youtube-video
source_date: 2022-05-13
url: https://www.youtube.com/watch?v=Fq6gqi9Ubog
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal, cloud-devops]
tags: [bash, scripting, automation, project, cron]
---

# this BASH script will KILL you.

## Summary

Fourth entry in NetworkChuck's Bash scripting series (framed as building the game
"Elden Ring" inside a Bash script — the "you died" screen). The clickbait title masks a
teaching video on **conditionals / if statements**. Chuck builds an interactive
text-adventure `eldenring.sh` step by step: the script prints `you died`, then prompts
the user through progressively harder "beast" battles decided by matching a random
number. Along the way he teaches: reading user input into variables, `if / else / fi`
syntax, comparison operators (`==`, `-gt`, etc.), logical OR (`||`) and AND (`&&`),
nested if statements, `elif`, and finally the `case` statement (a "switcher" he says
even his favorite language Python can't do as cleanly). The recurring gag is a hidden
"cheat code" — typing `coffee` wins any battle.

The lab is spun up on Linode (his sponsor / usual cloud provider) — a one-penny-per-hour
Ubuntu box, deleted when done, with the standard `$100 / 60-day free credit` plug. He
closes by pushing NetworkChuck Academy practice labs and noting these concepts transfer
to Python and other languages.

## Key claims (2022-05-13)

- The whole "game" is, at its core, a prepped executable script (`nano eldenring.sh`,
  add a shebang, `chmod +x`) that just runs `echo "You died"` — the Elden Ring death
  screen. (paraphrase)
- User input is captured with `read <varname>`: prompt with `echo`, then `read coffee`
  stores what the user types into the variable `coffee`. (paraphrase)
- A conditional / if statement lets a script make decisions and change behavior based on
  data — Chuck compares it to giving the script AI-like decision making. (paraphrase)
- Bash if-statement syntax: `if [[ $var == "y" ]]; then ... else ... fi`. Double square
  brackets with spaces inside, `==` for string equality, close the block with `fi`
  ("if" spelled backwards). (paraphrase)
- The first "beast" battle uses randomness: `beast=$(( RANDOM % 2 ))` produces 0 or 1;
  the player is asked to pick 0 or 1 (`read tarnished`), and if `beast == tarnished`
  the beast is vanquished — a 50/50 chance. (paraphrase)
- `$(( ... ))` denotes an arithmetic expression; `RANDOM % 2` yields 0–1, `RANDOM % 10`
  yields 0–9 — modulo sets the range. (paraphrase; references his earlier random-variable
  video)
- The boss "Margit" battle uses `RANDOM % 10` for a 1-in-10 chance, and `exit 1` is added
  after a loss so a dead player exits the script with that exit code and must restart.
  (paraphrase)
- Comparison operators beyond equality work in `[[ ]]`: greater-than, greater-or-equal,
  less-than, less-or-equal (demoed with `if [[ 2 -gt 1 ]]` printing "this is true").
  (paraphrase)
- Logical OR is `||` (double pipe): a condition like
  `[[ $beast == $tarnished || $tarnished == "coffee" ]]` wins if EITHER side is true —
  this is how the `coffee` cheat code is added. (paraphrase)
- Logical AND is `&&` (double ampersand): both conditions must be true, demoed by
  tightening the first battle with `&& [[ 47 -gt 23 ]]`. (paraphrase)
- Nested if: putting an if inside an if means BOTH must pass. Example — only the root
  user wins, via an inner `if [[ $USER == "root" ]]` inside the winning branch; a
  non-root user (Chuck adds user "Bernard", copies the script, `su Bernard`) fails the
  inner check and dies. (paraphrase)
- `elif` (else-if) offers an alternate branch when the first if is false — not both must
  be true (that's a nested if), just a second chance. Example: win if you have the coffee
  code, `elif [[ $USER == "Bernard" ]]` Bernard always wins, `else` you died. `elif`
  takes its own condition and `then` but no separate `fi`. (paraphrase)
- The `case` statement acts like a switcher on one variable and is cleaner than chained
  ifs/elifs for many branches. Syntax: `case $class in`, then `1)` ... `;;` per option,
  closed with `esac` ("case" reversed). Used to assign starting-class stats (samurai /
  prisoner / prophet each get different `type`, `HP`, `attack`, `magic` values), then
  echo the chosen class and stats. (paraphrase)
- `sleep 2` is used between battles to pace the game. (paraphrase)
- These conditional concepts transfer across languages — they look "very familiar" in
  his Python series. (paraphrase)
- Lab setup: Linode Ubuntu box, Dallas region, 1 GB Nanode plan, ~one penny per hour,
  deletable when finished; new users get $100 credit for 60 days. SSH in from Windows
  command prompt (or terminal on Mac/Linux). (paraphrase; sponsor/self-reported)

## Notable verbatim quotes

> "Get your coffee ready and prepare to die a lot, but also learn a lot."

> "If is one of the most powerful words ever. I love it. Especially in programming."

> "We're telling this Bash script to evaluate something... if something is true, is this
> true? And that's essentially what a conditional or an if statement is doing."

> "Fi. If backwards, if in reverse."

> "With these two pipes, I'm actually saying, hey, if beast equals tarnished, cool, it's
> true. Or, and that's what these two pipes mean. It means or."

> "Case is like an if statement, but it's more like a switcher and it's very simple."

> "This is something that even Python can't do. And Python's my favorite."

> "esac, just case in reverse."

> "To cement this into your brain, you need to practice it. You need to do it again, and
> again, and again until it becomes familiar to you, second nature."

> "Have you hacked the YouTube algorithm today? ... you gotta hack YouTube today,
> ethically of course."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
