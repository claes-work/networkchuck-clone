---
type: youtube-video
source_date: 2022-08-24
url: https://www.youtube.com/watch?v=nW9M0MQinfg
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal]
tags: [bash, scripting, project, loops, fun]
---

# a BASH script PUSH-UP counter (for #gains)

## Summary

Episode five of Chuck Keith's Bash scripting series, framed as a playful gag:
build a push-up counter script while "building up your Bash skills and your
muscles at the same time." The core teaching is **loops** in Bash — three kinds,
plus two loop-control keywords. Chuck starts with `while` loops (used to build the
actual push-up counter), moves to `until` loops (framed as the "upside down"
version of `while`), then `for` loops (his self-declared favorite), and finishes
with `break` and `continue`.

The push-up counter itself is a `while` loop that echoes a running count, then is
upgraded to use `read` so the user must press Enter for each rep, turning the
script into a real (if silly) workout. Along the way Chuck demos several practical
example scripts shipped in his Linode stack script: reading a file line-by-line
(the full text of Hamlet), a `while true` infinite loop (as a warning), a
coffee/tea `until` prompt, a `for` loop that pings a list of websites to check if
they're up, a `for` loop that curls the weather (`wttr.in`) for a list of cities
read from a file, an "internet is down" watcher using `while true` + `break`, and
an elevator script that uses `continue` to skip floor 13.

The lab runs on a Linode ($5/month) VM accessed over SSH; example scripts come from
Chuck's stack script (searchable as "NetworkChuck" in Linode). The episode credits
Sean Powers for the elevator `continue` example.

## Key claims (dated — the scripting concepts)

All dated 2022-08-24 (source publication).

- **`while` loops** repeat the body as long as a condition evaluates true.
  Structure: `while [[ condition ]]`, then `do`, the body, then `done`. Whatever is
  between `do` and `done` is what gets repeated.
- **Variables and integer comparison**: set a variable with `x=1`; the push-up
  loop's condition is `[[ $x -le 100 ]]` (loop while x is less than or equal to
  100). A variable is referenced with a `$` prefix (`$x`).
- **Incrementing a variable**: `(( x++ ))` adds one to `x` each pass — this is what
  eventually makes the `while` condition false and stops the loop.
- **`echo`** prints a string; variables inside the string are expanded (e.g. echo
  the current count of push-ups).
- **`read` for user input**: replacing `echo` with `read` pauses the loop for user
  input each iteration. `read -p "prompt"` shows a prompt; the flag `-p` supplies
  the prompt text. Used to force the user to press Enter per push-up rep.
- **Reading a file line-by-line**: a `while read` loop can iterate over each line
  of a file (demoed on a Hamlet text file, ~5,566 lines), looping as long as there
  is a line to read.
- **`while true` is an infinite loop** — because `true` is always true, the loop
  never ends on its own. Presented as dangerous; `Ctrl+C` stops it.
- **`until` loops** are the inverse of `while`: they run *until* a condition
  becomes true (loop while it's false). Same `do`/`done` structure. Demoed with a
  string comparison prompting for coffee/tea until the `order` variable equals
  `coffee`.
- **`for` loops** iterate over a list of items; the loop variable takes each item
  in turn (e.g. `for cups in 1 2 3 ... 10; do ...; done`). The variable "changes
  its identity" each pass.
- **Brace range expansion**: `{1..10}` is a shorthand for listing numbers 1 through
  10 individually in a `for` loop.
- **`for` over a list of strings**: iterate over website names, and combine with an
  `if` conditional (episode-4 knowledge) to `ping` each and report up/down. Ping
  options shown: quiet, count of 2, one-second wait, output suppressed; a
  successful ping response is treated as true.
- **`for` over command output**: a `for` loop's list can be the output of a command
  (e.g. `cat cities.txt`), so the loop variable becomes each line/item from that
  command. Demoed by curling `wttr.in/$x` to print the weather for each city.
- **`break`** immediately exits the loop. Demoed with a `while true` "is this host
  up yet" watcher that pings a target and breaks out the moment it responds;
  otherwise `sleep 2` and loop again — a cleaner alternative to a continuous ping
  while waiting for a rebooting server.
- **`continue`** skips the rest of the current iteration and moves to the next one
  (vs. `break`, which ends the loop entirely). Demoed with an elevator script that
  skips floor 13 (`if [[ $x -eq 13 ]]; then continue; fi`).

## Notable verbatim quotes

> This bash script is going to make you. Root.

> Welcome to bash episode five, where we are going to build up our bash muscles and our real muscles with something called loops.

> The wild loop will loop or repeat your script over and over. As long as something is true.

> So remember this key thing right here with our wild loops and which with every loop we're gonna do here in this video, what's going to be looped is between the do and the done. And you must put those to close it out.

> But you're lazy and weak. Take out the echo, take that sucker out. Now let's change that to read. And if you recall reading, it's how we get user input from our script.

> Because yeah, automation's cool. Except when it comes to your health, you probably shouldn't automate your health.

> Now let me warn you. Don't you mess around with wild loops. They can be dangerous.

> When you say wild, true, you're basically saying while true is true. It's, it's like, well, true. True. Well, that's always gonna be true. It's always going to run. People do use this. So be careful, but control C will always save the day.

> Now it's time for the upside down version of the wild loop. The until loop. It's the exact same thing. Just backwards, upside down.

> Now, time for the fun stuff, four loops these things you can get lost in.

> Each time the cups variable changed his identity based on our list in one loop, he was one in another loop, he was seven and that's the power of four loops.

> That's what break does. Otherwise or else it'll tell you, Hey, it's down and it will keep looping.

> SOAs break will just break out and be done. Continue is just a simple skip. It'll skip that loop and move on to the next loop.

> These are essential bash, scripting, things that you're gonna use all the time, they truly do unlock the power of bash scripting... And they're simply just, they're fun.

> Get your before and after pictures in order, you're about to get ripped from your wild loop.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT). (The elevator
`continue` example is credited to Sean Powers, but is presented and narrated by
Chuck.)
