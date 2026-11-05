# Custom Warmoth Telecaster No-Switch Mod

This repository contains the complete wiring and installation guide for a custom, minimalist **Warmoth Telecaster** mod. 

## The Story
This guitar originally started as a single-pickup beast with just a Seymour Duncan Hot Stack in the bridge and a pickguard cut for a solitary volume pot. Wanting to add a DiMarzio Muscle T single coil to the neck—but only possessing a clean, minimalist 2-hole control plate and a push-pull pot—this configuration avoids cutting the wood or adding a traditional blade selector switch entirely. 

By utilizing a DiMarzio EP1201PP 500k push-pull pot as a switchable master blender alongside a standard 500k volume pot, this layout unlocks pure neck, pure bridge, and parallel blend configurations seamlessly.

---

## System Logic & Profile
* **Push-Pull DOWN:** **Neck Pickup Only.** The bridge pickup and the blend loop are completely isolated.
* **Push-Pull UP:** **Bridge Pickup 100% On.** Rotating the knob clockwise blends the Neck pickup smoothly into the parallel mix.
* **Master Volume:** Dedicated exclusively to managing overall output level.

---

## ASCII Wiring Diagram

```text
===========================================================================================
                                  CUSTOM TELECASTER WIRING
===========================================================================================

       [ DI MARZIO NECK ]                    [ SEYMOUR DUNCAN BRIDGE ]
         (Muscle T Hot)                         (Hot Stack Hot)
               |                                       |
               | (Black Wire)                          | (Black Wire)
               v                                       v
     +-------------------+                   +-------------------+
     |    [ SWITCH ]     |                   |   [ BLEND POT ]   |
     |  L1     .     L2  |                   |                   |
     |  |            (X) |                   |  Term A  Term B  Term C
     |  +-JUMPER-+       |                   |    |       |       |
     |           |       |                   |    |       |       |
     |  L3  . . .|   L4  |                   |    |       |       |
     |           |   |   |                   |    |       |       |
     |  L5 <-----+   L6 <-------------------------+       |       |
     +--||-----------||--+                   +------------||------+
        ||           ||                                   ||
        ||           +-----------------------------+      ||
        v                                          v      v
   (Jump to Term C)                           (Jump to Term B & Output)
        |                                          |
        +------------------------------------------+

===========================================================================================
                            EP1201PP PIN-BY-PIN CONNECTIONS
===========================================================================================
 [ SHAFT FACES DOWN / AWAY FROM YOU ]

 +------------------------------------+
 |  [Lug 1] --------------> [Lug 2]   | <-- Top Row (Internal jumper links L1 to L5)
 |     |                    (Empty)   |
 |  JUMPER                            |
 |     |                              |
 |  [Lug 3] (Neck Hot)      [Lug 4]   | <-- Middle Row (L4 jumper routes to Term B)
 |     |                              |
 |  [Lug 5] <-------------- [Lug 6]   | <-- Bottom Row (L5 jumper routes to Term C)
 +-----||----------------------||-----+
       ||                      ||
       \/                      \/
 [Term A]                  [Term C]   <-- Pot Terminal C (From Switch Lug 5)
 (Empty)     [Term B]
                ||
                \/
       To Master Volume Lug 3
```

---

## Step-by-Step Installation Checklist

1. **Prep Extensions & Jumpers:** Cut three 1.5-inch insulated jumper wires using excess wire material. Ensure the Seymour Duncan's Red and White wires remain soldered together, insulated, and isolated.
2. **Solder Jumper 1 (Down-Position Signal Path):** Solder a small jumper wire connecting **Switch Lug 1** (Top Left) straight to **Switch Lug 5** (Bottom Left). This allows the pure neck pickup signal to route directly to the output path when the knob is pushed DOWN.
3. **Solder Jumper 2 (Blend Control Feed):** Connect **Switch Lug 5** straight down to **Pot Terminal C** on the base of the push-pull casing.
4. **Solder Jumper 3 (Switch Output Link):** Connect **Switch Lug 4** straight down to **Pot Terminal B** on the base of the push-pull casing.
5. **Connect Neck Pickup Hot:** Solder the DiMarzio Black wire (used as Hot for correct system phasing) directly to **Switch Lug 3**.
6. **Connect Bridge Pickup Hot:** Solder the Seymour Duncan Black wire directly to **Switch Lug 6**.
7. **Run System Master Output:** Solder a lead wire alongside Jumper 3 into **Pot Terminal B**. Route the opposite end of this wire directly to **Lug 3 of your standard Master Volume Pot**.
8. **Establish System Common Grounds:** Solder the DiMarzio Neck White and Grey/Bare wires directly to the casing of the Master Volume pot. Ensure the Duncan Green/Bare wires, output jack ground, and bridge ground wires are securely connected to the common ground plane on the pot backs.

---

## Pre-Assembly Functional Test

Plug the guitar into an amplifier at low volume before re-fastening the control plate:
* **Knob Pushed DOWN:** Tap the neck pickup poles with a screwdriver. It should click cleanly through the amp, while the bridge pickup remains entirely silent.
* **Knob Pulled UP:** Tap the bridge pickup poles to confirm it is active. Turn the blend pot clockwise to verify the neck pickup smoothly fades into parallel matrix operation.