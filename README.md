# Rep Caller

A tiny web app that calls out exercise repetitions so you can keep count without watching a clock. Define a list of exercises; for each one, the app announces the name, then counts down aloud from your chosen number at your chosen pace.

It runs entirely in the browser as a single HTML file — no server, no account, no install. Your routines are stored locally on your phone and never leave it.

## Using it on Android

1. Open the app's URL in Chrome.
2. Tap the ⋮ menu → **Add to Home screen**. It will launch full-screen like a normal app.
3. Tap **Start**. (Sound only works after a tap — that's a browser rule, not a bug.)

The screen stays awake during a workout, but must stay on: if you blank the screen with the power button, counting pauses until you wake it. Prop the phone up where you can see the countdown.

## Defining a routine

Tap **Edit**. One exercise per line, three parts separated by commas:

```
Name, count, seconds-per-count
```

For example:

```
Squats, 20, 2
Lunges, 10, 5
```

This announces "Squats", then counts 20 down to 0 speaking one number every 2 seconds, then moves on to Lunges.

Notes:

- The name can be a whole phrase — `And now for squats, 10, 2` is spoken (and displayed) in full. No commas within the name, since commas separate the three parts. Full stops in the name create spoken pauses.
- Seconds can be decimal (`1.5`).
- **Save routine** stores the list on your phone. **New** creates another routine (e.g. Morning / Evening); switch between routines with the dropdown in the header. **Delete** removes the current routine (you always keep at least one).

## Choosing a voice

On the Edit screen, the **Voice** dropdown lists every text-to-speech voice your phone's browser offers, in many languages. Pick one and tap **Test** to hear it. The voice reads whatever you wrote: choose a Spanish voice and the countdown is in Spanish — write the exercise names in Spanish too and the whole session is. Handy if you're learning a language and want your numbers drilled twice a day.

More voices can be added to the phone under Settings → Text-to-speech output → your engine → Install voice data.

## During a workout

- **Pause / Resume** — pauses the count where it is.
- **Skip** — jumps to the next exercise.
- **Stop** — ends the session.
- The progress bar under the number shows how far through the current exercise you are.

## Where your data lives

Routines and the voice choice are kept in the browser's localStorage under the key `repCallerProfiles`, on your device only. Nothing is sent anywhere. Two consequences:

- Different browsers or devices each have their own separate routines — nothing syncs.
- Clearing the browser's site data erases your routines. They're short, so keep a copy of the lines in a notes app if you'd miss them.

## Hacking on it

Everything — markup, styles, logic — is in `index.html`. Edit it on GitHub, commit, and the live site updates in about a minute. Your saved routines survive app updates, since they live in your browser, not in the file.
