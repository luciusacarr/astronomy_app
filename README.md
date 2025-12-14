# Solar System Tracker

## Overview

**Solar System Tracker** is a time-accurate solar system simulation and mobile application developed over approximately **three weeks (\~80 hours)**. What began as a physics-based orbital model evolved into a full-featured interactive app capable of tracking the **real-time positions of all eight planets** and providing observational data such as **rise/set times**, **azimuth**, **altitude**, and **exact sky location**.

The project combines orbital mechanics, astronomical algorithms, and mobile development to bridge theoretical astronomy with real-world sky observation.

---

## Motivation

The original goal was to build a physically accurate solar system model using:

- Orbital eccentricity
- Planetary distances
- Velocity variation along orbits

Later, while camping and observing the night sky, the project shifted focus toward **practical sky identification**: determining which visible "stars" were actually planets. This motivated a transition from a desktop simulation to a **mobile astronomy tool**.

---

## Early Model

The initial implementation:

- Used almanac data for planetary distances
- Modeled orbits in 2D using sine and cosine
- Calculated speeds without time-dependence

This produced a visually correct but **time-independent** simulation of planetary motion.

---

## Time Synchronization Challenges

The main challenge was syncing planetary positions with **real-world time**.

Attempts included:

- Mean orbital velocities (inaccurate over time)
- Iterative velocity refinement (computationally expensive)

Neither approach scaled well or produced sufficient accuracy.

---

## Orbital Solution: VSOP87

After studying *Astronomical Algorithms* by **Jean Meeus**, the project adopted the **VSOP87** planetary theory model.

This enabled:

- Accurate heliocentric planetary positions
- Time-based calculations using the **Julian Date**
- Reliable long-term precision

---

## Mobile App Implementation

The app was developed using:

- **Flutter** (UI framework)
- **Dart** (application logic)

Key features include:

- Calculation of the current **Julian Date**
- Heliocentric Cartesian coordinates for all planets
- Interactive solar system view with **zooming and panning**

---

## Coordinate Transformations

To enable sky observation features, coordinates were converted from:

**Heliocentric → Geocentric**

From geocentric coordinates, the app computes:

- **Right Ascension (RA)**
- **Declination (Dec)**

These values allow precise sky positioning for any observer on Earth.

---

## Observer-Based Calculations

Using the observer's **latitude and longitude**, the app calculates:

- **Azimuth** – direction relative to true north
- **Altitude** – height above the horizon
- **Rise and set times** for planets and the Sun

These values are critical for real-world sky tracking.

---

## Interactive UI Features

- Planet selection with real-time data display
- Informational overlay showing planetary stats
- Compass-based **guide mode** using phone sensors

### Guide Mode

- Arrow points toward the selected planet
- Vertical alignment bar shrinks as accuracy improves
- Allows real-time physical alignment with celestial objects

---

## Field Testing

The app was tested outdoors under real night-sky conditions.

Results:

- Planet identification was accurate
- Directional guidance matched real observations
- Successfully identified planets visible to the naked eye

---

## Current Status & Future Work

The project continues to evolve and expand in scope.

Completed additions:

- The **Moon** has been fully integrated into the model
- Accurate **lunar phases** are calculated and displayed
- An **Earth-side indicator** shows which side of the Earth the observer is on relative to the Moon and Sun

Planned improvements:

- App Store release preparation
- Additional celestial objects

---

## App Development & Deployment Experience

Beyond the physics and astronomy, this project required learning the full lifecycle of mobile app development, particularly for iOS deployment. Key areas included:

- **Project structure and build systems** in Flutter/Dart
- Managing platform-specific configuration files for iOS
- Understanding code signing, provisioning profiles, and certificates
- Preparing assets and metadata required for App Store submission
- Debugging platform-specific issues that did not appear in simulators
- Performance profiling and memory management on real devices
- Iterative bug testing and validation across different devices and OS versions

This aspect of the project highlighted the gap between a working prototype and a production-ready application, and provided valuable experience in packaging, testing, and maintaining a scientific app for real-world users.

---

## What I Learned

- Orbital mechanics and celestial coordinate systems
- Astronomical time standards (Julian Date, epochs)
- VSOP87 planetary modeling
- Sensor integration in mobile devices
- End-to-end scientific app development
- Mobile app deployment, testing, and release workflows

