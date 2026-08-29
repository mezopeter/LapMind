# How LapMind got here

This is a development story, not a release changelog. It records why the
project changed direction and which real-world problems shaped it. Dates are
included only where the private Git history or physical test evidence supports
them.

## The beginning — HUD off needed a voice

LapMind began with a personal problem: driving GT7 with less or no HUD was more
immersive, but important race information disappeared with it. Looking at a
phone was not a solution, especially for VR. The useful output had to be a
voice in the driver's ear.

The early Android prototypes established the basic path:

```text
GT7 telemetry → Android → race state → spoken callout
```

They learned to receive and decode GT7 telemetry, show lap and position data,
estimate fuel from completed usable laps, select local Android voices, and
avoid speaking over themselves.

## Before the recorded checkpoint — from demo to tool

The project moved beyond a talking telemetry display. It gained saved
PlayStation profiles, configurable callouts, local TTS controls, fuel warnings,
track and car recognition, and the beginnings of session memory.

The difficult part was not producing sentences. It was deciding when a
sentence was true, current and useful.

## 25 August 2026 — the first durable baseline

The private repository begins with the `0.5.1-diagnostic-alpha` baseline. From
that point, physical test observations started driving the architecture more
strictly.

The app gained a clearer race lifecycle, an offline car database and two local
haptic meanings. Session handling became a product feature rather than a debug
side effect.

## 25–26 August 2026 — physical tests changed the voice

Short real races exposed problems that unit tests alone could not:

- final laps could be lost or fabricated;
- auto-drive and results packets could be mistaken for racing;
- useful calls could arrive late behind an Android speech queue;
- Pause, Resume and Exit needed different meanings;
- track identity could flicker at inconvenient moments;
- timed-race elapsed estimates did not share GT7's visible event clock;
- a phone call could interrupt audio and leave stale messages behind.

The answer was a semantic priority queue, lifecycle-aware retention, explicit
finish barriers, conservative track confidence, audio-focus handling and more
diagnostic evidence. The app became quieter where the evidence was weak.

A small zero-fuel joke chain also appeared during this period. Not every piece
of telemetry work had to be solemn.

## 26 August 2026 — Discord became real

Discord had always been connected to the original use case: getting the
engineer into a PlayStation/VR audio path without requiring a PC. A separate
Android Discord companion proved that encrypted bot voice could be produced
from the phone.

The integration was deliberately isolated. Discord could receive semantic
engineer messages, but its network, token, reconnect or voice failures were not
allowed to stop telemetry, local TTS, haptics or sessions.

## 27 August 2026 — portable sessions and one app

`0.6.1-alpha1` brought the optional Discord companion into the same APK and
added versioned, secret-free session backup, restore, export and import.

This made the local-first principle concrete: useful personal history could be
kept and moved without turning LapMind into a mandatory cloud service.

## 28–29 August 2026 — diagnostics became an instrument

The first replay/reference experiments showed that a 5 Hz debug sample was
enough to prove that telemetry existed, but not enough for precise lines,
braking points or apex analysis.

The app therefore gained an explicit full-rate recorder with bounded storage,
a separate writer thread, markers and a schema-versioned export. A physical PS4
capture recorded 38,646 Packet C samples without recorder drops. It also
exposed lifecycle and clock problems that would otherwise have remained hidden.

The next build fixed the mixed Android clock domains. A later physical control
proved the elapsed clock, time limit and notification STOP path.

## 29 August 2026 — Track Lab, then humility

`0.6.2-alpha1` introduced the first experimental Track Lab vertical slice: an
offline trace model, local diagnostics import, track geometry seeds, speed and
brake/throttle views, zoom, pan and point inspection.

The first physical UI test was encouraging and rough. It also made the real
product question clearer: drawing telemetry is easy; helping someone understand
one corner is harder.

On the same day, focused market research found several actively developed GT7
companions, voice engineers and telemetry/coaching tools moving in remarkably
similar directions. That discovery was briefly demoralising. It also validated
the original problem.

The decision was not to enter a feature-count war. LapMind would concentrate on
its own workflow:

```text
Drive → Review → Understand → Practise → Drive
```

## The beta decision

The complete long-term Track Lab vision should not hold the useful core
hostage. The first controlled beta will focus on stable voice, optional Discord
and local sessions. Track Lab will be present only as an explicitly experimental
preview whose future is shaped by real use.

That is where this public repository begins.
