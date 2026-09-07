# How LapMind got here

This is a development story, not a release changelog. It records why the
project changed direction and which real-world problems shaped it. Dates are
included only where the private Git history or physical test evidence supports
them.

## The beginning — Honda RA272, Le Mans, HUD off

LapMind began with one very specific drive.

I wanted to take the **1965 Honda RA272 around Le Mans in VR** and have nothing
between me and the car: the cockpit, the track, the engine, me. No floating fuel
gauge, no lap counter, no bright interface sitting over a sixty-year-old racing
car.

GT7 can make that feel wonderful with the HUD out of the way. The problem is
that once the HUD disappears, some information that genuinely matters disappears
with it too.

Looking at a phone was not the answer. I did not want another dashboard. I just
wanted someone to tell me the important bits.

That became LapMind.

The original hardware setup was **PS5 + PSVR2 + Sony INZONE Buds**. Because that
headset cannot simultaneously provide PS5 2.4 GHz audio and Android Bluetooth
audio, Discord became the practical path for putting LapMind's engineer into the
same headset as GT7 without adding a PC.

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

Discord was connected to the original use case from the beginning: getting the
engineer into the same PlayStation/VR audio path as GT7 without requiring a PC.
A separate Android Discord companion proved that encrypted bot voice could be
produced from the phone.

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
similar directions. That discovery briefly made the project look less unique.
It also clarified what mattered.

The decision was not to enter a feature-count war. LapMind would concentrate on
its own workflow:

```text
Drive → Review → Understand → Practise → Drive
```

## The beta decision

The complete long-term Track Lab vision should not hold the useful core
hostage. The first controlled beta focuses on the voice engineer, optional
Discord and local sessions. Track Lab remains explicitly experimental while its
future is shaped by real use and evidence.

## 31 August 2026 — owned evidence changed the model

Repeated physical testing at High Speed Ring and Monza exposed a misleading
assumption: a Time Trial ghost could make GT7's car count look competitive even
though the driver was still in a solo practice context. That explained false
P1 behaviour and showed that a session's activity and the way it ends are not
the same thing.

LapMind now treats activity type separately from completion state. A confidently
recognized practice session can simply end without pretending to be a failed
race; unusual or incomplete evidence remains unknown rather than being forced
into a confident label.

The same owned telemetry changed Track Lab. Unconstrained spatial matching could
jump to the wrong place on a lap, so progress-constrained distance alignment
became the comparison spine. Track Lab gained richer telemetry inspection,
automatically derived analytic segments and descriptive owned-lap comparison,
while retaining its experimental boundary.

The app presentation also moved away from its developer-alpha roots: Settings
became hierarchical, Sessions began with browsing rather than administration,
and the launcher and information hierarchy were prepared for a controlled beta.

## 3–7 September 2026 — the product became calmer

The V4-era UI work concentrated on making LapMind feel less like a developer
tool and more like the quiet instrument it is supposed to be.

Sessions, Settings, Discord Companion presentation and the Race Engineer &
alerts UI went through physical owner review. The Session package also passed a
real round trip:

**Analyse → Export → Delete → Import → Analyse**

That was an important local-first checkpoint: a session could genuinely leave
the local store, be deleted, come back, and still remain useful for analysis.

Track Lab received a more focused product direction as well. Instead of exposing
every analytical control at once, the current model is:

**Track overview → corner / section focus → point inspect**

It remains experimental.

## September 2026 — Corner Lab became research, not just an idea

Circuit Experience turned out to be useful not because LapMind should recreate
it, but because GT7 already gives the driver repeated, structured pieces of the
same track.

Owned full-rate captures showed that repeated short sections could be recovered
as spatial families and mapped back onto a longer lap. A second owned capture
reproduced the structural result, and a reusable offline prototype replayed both
captures successfully.

That moved Corner Lab out of the raw-idea category and into a genuine
**planned / researched** direction.

It did not make Corner Lab a product feature overnight. Reduced-rate robustness,
production persistence, Stable Fast, coaching and broader generalization still
need their own evidence.

The lesson remains the same as it was in the first week: measured evidence
should change the model before the product changes its claims.
