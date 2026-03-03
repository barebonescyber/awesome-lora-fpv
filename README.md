# Awesome LoRa Mesh & FPV Drones

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of beginner-friendly resources for learning LoRa mesh networking (Meshtastic and MeshCore) and hobbyist FPV drones (Commercial off-the-shelf and 3D printed builds).

This repository focuses on decentralized mesh communication and hobbyist drone building. Resources are selected specifically for beginners seeking practical, hands-on learning.

## Contents

- [LoRa Mesh Networking](#lora-mesh-networking)
- [Meshtastic](#meshtastic)
- [MeshCore](#meshcore)
- [LoRa Hardware](#lora-hardware)
- [LoRa Software & Tools](#lora-software--tools)
- [Antennas & Range Optimization](#antennas--range-optimization)
- [LoRa Communities](#lora-communities)
- [LoRa Tutorials & Guides](#lora-tutorials--guides)
- [FPV Drones](#fpv-drones)
- [Commercial FPV Kits](#commercial-fpv-kits-rtfbnf)
- [DIY Build Kits](#diy-build-kits)
- [3D Printed Drones](#3d-printed-drones)
- [Essential Components](#essential-components)
- [FPV Software & Configuration](#fpv-software--configuration)
- [FPV Communities](#fpv-communities)
- [FPV Tutorials & Build Guides](#fpv-tutorials--build-guides)

## LoRa Mesh Networking

LoRa (Long Range) is a wireless modulation technique enabling long-distance, low-power communication. Unlike traditional radio or cellular networks, LoRa mesh networks create decentralized communication systems where each device can relay messages for others - no central infrastructure required.

**Essential Reading**
- [What Is LoRa? The Complete Beginner's Guide](https://blog.paessler.com/what-is-lora-a-beginners-guide-part-1) - Comprehensive introduction to LoRa technology, characteristics, and implementation basics.
- [Meshtastic Official Documentation](https://meshtastic.org/docs/introduction/) - Getting started with mesh networking fundamentals.
- [Understanding LoRa Technology](https://www.seeedstudio.com/blog/2025/07/15/what-is-lorawan-beginners-guide/) - Technical primer on modulation, frequency, and range.

**Key Characteristics**
- **Range**: 2-5km urban, up to 15km rural, 50km+ line-of-sight with proper antennas.
- **Power**: 10+ year battery life possible with optimized settings.
- **Data Rate**: 0.3-50 kbps (designed for messages, not streaming).
- **Frequency**: 868 MHz (EU), 915 MHz (US), 433 MHz (Asia).
- **Security**: AES-128 encryption standard.
- **Mesh Topology**: Each node relays messages, creating resilient networks.

**Why Mesh Networking?**
- Off-grid communication (hiking, events, emergencies).
- No cellular coverage required.
- Community-owned infrastructure.
- Privacy-focused (encrypted, decentralized).
- Educational platform for RF and networking concepts.

## Meshtastic

Meshtastic is an open-source, off-grid mesh communication platform built on LoRa radios. It's the most popular beginner-friendly mesh networking project, perfect for hiking, events, emergency communications, and learning about distributed systems.

**Official Resources**
- [Meshtastic Official Documentation](https://meshtastic.org/docs/getting-started/) - Complete getting started guide for all devices.
- [Meshtastic GitHub Repository](https://github.com/meshtastic/firmware#readme) - Source code, firmware releases, and issue tracking.
- [Meshtastic Discord](https://discord.com/invite/ktMAKGBnBs) - 50k+ member community for real-time support.
- [Web-Based Flasher](https://flasher.meshtastic.org) - Easiest way to flash firmware to ESP32 devices (no installation needed).

**Beginner Guides**
- [Meshtastic: The Complete Getting Started Guide (2026)](https://adrelien.com/meshtastic-the-complete-getting-started-guide/) - Comprehensive setup walkthrough including hardware selection, firmware flashing, and first messages.
- [Meshtastic Beginners Guide - JKPG Mesh](https://jkpg-mesh.se/blogs/blog20.html) - Explores learning opportunities including electronics, RF fundamentals, and practical applications.
- [Best Meshtastic Devices for Beginners (2026)](https://www.youtube.com/watch?v=N8OOw5HIfA8) - Hardware recommendations and starter guide.

**Key Features**
- **True mesh networking** - All clients participate in routing (not hub-and-spoke).
- **Default hop limit**: 3 (configurable up to 7).
- **Mobile-optimized** - Excellent for moving groups and ad-hoc networks.
- **Rich telemetry** - GPS tracking, environmental sensors, battery monitoring.
- **Multiple radio presets** - LongFast, MediumFast, ShortFast, LongSlow.
- **Cross-platform apps** - iOS, Android, Web, Python CLI.
- **Plugin ecosystem** - Position tracking, messaging, environmental monitoring.

**Radio Presets Explained**
- **LongFast** - Best balance of range and speed (default, ~6.5km typical).
- **LongSlow** - Maximum range, slower messages (~12km+ possible).
- **MediumFast** - Higher throughput for dense areas (~3km).
- **ShortFast** - Highest data rate for close proximity (~1.5km).

**Use Cases**
- Hiking and outdoor adventures.
- Music festivals and large events.
- Neighborhood emergency networks.
- Learning RF propagation and mesh networking.
- Remote monitoring (weather stations, sensors).

## MeshCore

MeshCore is an alternative mesh protocol optimized for large-scale, fixed-infrastructure networks. Unlike Meshtastic's peer-to-peer approach, MeshCore separates **repeaters** (routing-only nodes) from **companions** (end-user devices), enabling massive city-scale meshes.

**Official Resources**
- [Austin Mesh - MeshCore vs Meshtastic](https://www.austinmesh.org/learn/meshcore-vs-meshtastic/) - Detailed technical comparison of routing strategies, hop limits, and architectural decisions.
- [LoRa Mesh Devices - Meshtastic vs MeshCore](https://www.lorameshdevices.com/blog/meshcore/meshtastic-vs-meshcore-key-differences-explained.html) - Key differences in firmware and network design.
- [MeshCore GitHub](https://github.com/armooo/meshcore#readme) - Source code and technical documentation.

**Key Features**
- **Infrastructure-focused** - Fixed repeaters form network backbone.
- **High hop limit** - Up to 64 hops (vs Meshtastic's 7).
- **Flood-then-direct routing** - Initial broadcast followed by optimized paths.
- **Lower telemetry overhead** - Minimal GPS/sensor data for better message throughput.
- **Faster multi-hop delivery** - Optimized for urban fixed infrastructure.
- **Narrower bandwidth** - 62.5 kHz (vs Meshtastic's typical 250 kHz).

**Architecture Comparison**

| Aspect | Meshtastic | MeshCore |
|--------|-----------|----------|
| **Node types** | All nodes equal | Repeaters + Companions |
| **Max hops** | 7 | 64 |
| **Routing** | Flood routing | Flood-then-direct |
| **Telemetry** | Rich (GPS, sensors) | Minimal |
| **Best for** | Mobile groups, ad-hoc | Fixed city infrastructure |
| **Setup complexity** | Beginner-friendly | Intermediate |
| **Use case** | Hiking, events, learning | City-wide networks |

**When to Choose MeshCore**
- Building permanent city/region-scale networks.
- Deploying fixed solar repeaters.
- Prioritizing message delivery over telemetry.
- Need for extreme hop counts (20+ hops).
- Experienced with networking concepts.

**When to Choose Meshtastic**
- Getting started with mesh networking.
- Mobile groups (hiking, biking, events).
- Want rich telemetry and position tracking.
- Prefer easier setup and configuration.
- Active development and larger community.

**Compatible Hardware**
Both platforms run on similar ESP32-based devices:
- Heltec V3/V4.
- LilyGo T-Beam/T-Echo/T-Deck.
- RAK WisBlock.
- Seeed Studio devices.

## LoRa Hardware

### Recommended Beginner Devices

**Budget Tier ($25-40)**
- **Heltec V3** ($25-35) - Most popular ESP32 board, OLED display, GPS-ready. Widely supported, excellent community documentation. Optional GPS module ($15-20 extra). Best for: First-time builders wanting maximum support.
- **Heltec V4** ($30-40) - Upgraded version with better power management. Improved WiFi/BT performance. Better battery life. Best for: Slightly higher budget, latest features.

**Plug-and-Play ($40-60)**
- **Seeed Studio Wio Tracker 1110** ($40-50) - Pre-flashed, ready out of box. No firmware flashing required. Built-in GPS. Best for: Absolute beginners wanting zero configuration.

**All-in-One Communicators ($50-80)**
- **LilyGo T-Deck** ($60-70) - ESP32 with built-in keyboard, screen, and trackball. Send messages without phone. Full QWERTY keyboard. Best for: Phone-free operation.
- **LilyGo T-Echo** ($50-60) - E-ink display, ultra-low power. Weeks of battery life. Sunlight-readable screen. Best for: Extended deployments.

**Portable with GPS ($35-50)**
- **LilyGo T-Beam** ($35-45) - ESP32 with integrated GPS and 18650 battery holder. Complete portable package. Expandable battery options. Best for: Hiking and mobile use.

**Advanced/Modular ($60-100)**
- **RAK WisBlock Meshtastic Starter Kit** ($70-90) - Modular system with expansion slots. Add sensor modules (temperature, pressure, air quality). Professional build quality. Best for: Expandable sensor networks.

### Antenna Considerations

**Stock Antennas**
- Most devices include basic 2-3 dBi antennas sufficient for getting started.

**Upgrade Options**
- **3-5 dBi omni** ($10-20) - Better all-around range.
- **8-10 dBi directional** ($20-40) - Point-to-point long distance.
- **DIY builds** - J-pole, dipole, yagi designs available online.

**Critical:** Always use proper 915 MHz (US) or 868 MHz (EU) antennas matched to your region.

### Solar Repeater Components

For permanent infrastructure nodes:

**Power System**
- 10-20W solar panel ($20-40).
- 18650 battery holder or LiPo battery pack.
- Solar charge controller ($10-15).
- Weatherproof enclosure ($15-30).

**Guides**
- [DIY Solar Repeater Build](https://www.austinmesh.org/learn/diy-solar-repeater/) - Complete construction guide.

## LoRa Software & Tools

**Firmware Flashing**
- [Meshtastic Web Flasher](https://flasher.meshtastic.org) - Browser-based, easiest method (Chrome/Edge recommended).
- [Meshtastic Python CLI](https://github.com/meshtastic/python#readme) - Command-line tool for advanced configuration. Install: `pip install meshtastic`. Essential for scripting and automation.

**Mobile & Desktop Apps**
- [Meshtastic Android App](https://play.google.com/store/apps/details?id=com.geeksville.mesh) - Full-featured companion app.
- [Meshtastic iOS App](https://apps.apple.com/us/app/meshtastic/id1586432531) - iOS companion with mapping.
- [Meshtastic Web Client](https://client.meshtastic.org) - Browser-based interface (Beta).

**Configuration Tools**
- **Python CLI** - Most powerful for bulk configuration.
- **Mobile Apps** - Best for day-to-day adjustments and monitoring.
- **Web Interface** - Some devices support direct WiFi configuration.

**Visualization & Mapping**
- [Meshtastic Official Map](https://meshtastic.org/map) - Global node map with public nodes.
- [meshview.armooo.net](https://meshview.armooo.net/) - Alternative visualization with enhanced features.
- [Meshmap](https://meshmap.net) - Community-driven mapping project.

**Development & Integration**
- [Meshtastic.js](https://github.com/meshtastic/meshtastic.js#readme) - JavaScript library for web applications.
- [Meshtastic Python API](https://meshtastic.org/docs/software/python/cli/) - Python library for automation.
- [MQTT Integration](https://meshtastic.org/docs/software/mqtt/) - Connect mesh to internet services.

## Antennas & Range Optimization

**Antenna Basics**
- **dBi Rating** - Higher = more gain (3 dBi typical stock, 5-9 dBi upgrades).
- **Omnidirectional** - 360° coverage, good for mobile/general use.
- **Directional** - Focused beam, better point-to-point range.

**Popular Upgrades**
- **915 MHz 5.8 dBi Omni** ($15-25) - Noticeable improvement over stock.
- **915 MHz 8 dBi Directional** ($25-40) - Double+ range in one direction.
- **Magnetic base antennas** ($20-35) - Vehicle mounting made easy.

**DIY Antenna Projects**
- [1/4 Wave Ground Plane Antenna](https://meshtastic.org/docs/hardware/antennas/antenna-testing/) - Simple wire antenna.
- [J-Pole Design](https://www.qsl.net/kd4sai/jpole.html) - Better performance, still DIY-friendly.
- [Yagi Directional](https://www.qsl.net/yo4tnv/docs/Yagi%20Calculator%202.0.htm) - Maximum range for fixed links.

**Range Optimization Tips**
1. **Height is everything** - Every meter of elevation matters exponentially.
2. **Line of sight** - Obstacles absorb LoRa signals (trees, buildings, hills).
3. **Antenna placement** - Get antenna outdoors and as high as possible.
4. **Ground plane** - Ensure proper ground plane for optimal radiation pattern.
5. **Cable loss** - Use shortest, highest-quality coax possible.
6. **Settings** - LongSlow preset for maximum range.

**Real-World Range Expectations**
- Handheld to handheld (urban): 0.5-2 km.
- Handheld to fixed repeater: 3-8 km.
- Fixed repeater to repeater: 10-20 km.
- Optimal conditions (hilltop to hilltop): 50+ km.

## LoRa Communities

**Meshtastic Communities**
- [Meshtastic Discord](https://discord.com/invite/ktMAKGBnBs) - 50k+ members, most active community. Real-time support channels, regional mesh channels, development discussions.
- [Meshtastic Reddit](https://www.reddit.com/r/meshtastic/) - 20k+ members, project discussions.
- [Meshtastic Forum](https://meshtastic.discourse.group/) - Long-form discussions and guides.

**MeshCore Communities**
- [MeshCore Reddit](https://www.reddit.com/r/meshcore/) - Growing community for infrastructure meshes.
- [Austin Mesh](https://www.austinmesh.org/) - MeshCore-based regional network example.

**Regional Mesh Networks**
- [NYC Mesh](https://www.nycmesh.net/) - New York City community network.
- [Seattle Meshnet](https://seattlemesh.net/) - Pacific Northwest mesh community.
- [Austin Mesh](https://www.austinmesh.org/) - Texas mesh network.
- [Find Local Groups](https://meshtastic.org/docs/community/) - Directory of regional meshes.

**Learning & Support**
- [Meshtastic Documentation](https://meshtastic.org/docs/) - Comprehensive official docs.
- [GitHub Discussions](https://github.com/meshtastic/firmware/discussions) - Technical Q&A.
- Amateur Radio clubs - Many hams experiment with Meshtastic.

## LoRa Tutorials & Guides

**Setup & First Steps**
- [Complete Meshtastic Setup Guide](https://meshtastic.org/docs/getting-started/) - Official quickstart.
- [Heltec V3 Setup Walkthrough](https://www.youtube.com/watch?v=MN4YUHjJtrk) - Video tutorial for most popular device.
- [LilyGo T-Beam Configuration](https://meshtastic.org/docs/hardware/devices/lilygo/) - GPS setup and battery management.

**Building Fixed Infrastructure**
- [DIY Solar-Powered Repeater](https://www.austinmesh.org/learn/diy-solar-repeater/) - Permanent mesh node construction.
- [Outdoor Weatherproofing Guide](https://meshtastic.org/docs/hardware/weatherproofing/) - Protecting your nodes from elements.
- [Optimal Repeater Placement](https://www.austinmesh.org/learn/optimal-placement/) - Siting strategies for maximum coverage.

**Advanced Configuration**
- [Channel Configuration Guide](https://meshtastic.org/docs/configuration/radio/channels/) - Multi-channel setup.
- [MQTT Bridge Setup](https://meshtastic.org/docs/software/mqtt/) - Connect mesh to internet.
- [Sensor Integration](https://meshtastic.org/docs/configuration/module/telemetry/) - Adding environmental sensors.
- [Position Tracking](https://meshtastic.org/docs/configuration/module/position/) - GPS and mapping configuration.

**RF & Antenna Guides**
- [Understanding LoRa Modulation](https://meshtastic.org/docs/overview/radio-settings/) - Technical deep dive.
- [Antenna Testing Methodology](https://meshtastic.org/docs/hardware/antennas/antenna-testing/) - Measure real-world performance.
- [Range Testing Guide](https://meshtastic.org/docs/configuration/module/range-test/) - Built-in range test module.

## FPV Drones

First-person view (FPV) drones allow pilots to fly as if seated in the cockpit, using video goggles for real-time flight perspective. This immersive experience is ideal for racing, freestyle aerial acrobatics, and cinematic video capture.

**Essential Reading**
- [How To Get Started With FPV Drone](https://oscarliang.com/fpv-drone-guide/) - Comprehensive tutorial covering building, flying, and tuning.
- [FPV Drones In 2026: How to Start Flying](https://www.youtube.com/watch?v=GGsbm1DhFbc) - Complete beginner roadmap.
- [FPV Drone Beginner's Guide](https://www.mepsking.shop/blog/fpv-drone-beginners-guide.html) - 2026 guide covering types, components, and setup.

**Learning Path**
1. **Get a simulator** - Cheapest and safest way to learn (10+ hours recommended).
2. **Choose your path** - RTF (Ready-to-Fly), DIY kit, or 3D printed.
3. **Practice in Acro mode** - Master manual control before buying hardware.
4. **Build/Buy beginner drone** - Budget for 100+ crashes.
5. **Join community** - Learn from experienced pilots.

**Key Terminology**
- **RTF** (Ready-to-Fly) - Complete package, just charge and fly.
- **BNF** (Bind-and-Fly) - Needs compatible controller and goggles.
- **DIY Kit** - Build it yourself, learn components.
- **Analog vs Digital** - Analog is cheaper, Digital (DJI/Walksnail) gives HD.
- **Whoop** - Small ducted drone, indoor-friendly.
- **5-inch** - Standard racing/freestyle size.

## Commercial FPV Kits (RTF/BNF)

**Best Starter Kits**
- **BETAFPV Cetus X RTF Kit** ($159) - Indoor whoop with LiteRadio2 SE and VR02 goggles. Best for: Indoor flying, true beginners. Includes: Drone, controller, goggles, batteries.
- **EMax Tiny Hawk III Bundle** ($239) - Popular analog RTF kit. Best for: Beginner outdoor/indoor, proven reliability. Easy parts availability and troubleshooting.
- **EMAX EZ Pilot Pro Kit** ($239) - Improved frame, 200mW VTX. Includes: Drone, Transporter 2 goggles, E8 transmitter.
- **DJI Avata 2** ($999+) - Premium digital FPV. Best for: Cinematic filming, safety features. Includes: DJI O4 video, Motion Controller, Goggles.

**Whoop Drones (Tiny, Indoor-Friendly)**
- **HGLRC Draknight 2" RTF** ($199) - Small spaces specialist.
- **BetaFPV Cetus** - Brushed motors, turtle mode, auto-landing.

## DIY Build Kits

**Joshua Bardwell Kits** (Highly Recommended)
- **QAV-S Joshua Bardwell SE 3"** ($249) - Sub-250g analog build. Includes frame, motors, flight stack, camera, VTX. Complete video build guide by Joshua Bardwell. Best for: Learning to build, staying under FAA 250g limit.
- **QAV-S 2 5" HD Ready** ($299) - Full-size freestyle. DJI O3/Walksnail compatible. Best for: Serious beginners wanting HD. Comprehensive video tutorials included.

**Why Bardwell Kits?**
- Everything is compatible (no guesswork).
- Step-by-step video guidance.
- Learn to build AND fix your drone.
- Foolproof parts selection.

**What You'll Still Need**
- Video system (analog or DJI/Walksnail).
- FPV goggles.
- Radio controller.
- Batteries (LiPo 4S or 6S).
- ELRS receiver.
- Spare parts (props, arms, hardware).

## 3D Printed Drones

**Benefits of 3D Printing**
- **Customization** - Design frames for specific needs.
- **Cost-effective** - One spool of filament = dozens of frames.
- **Rapid iteration** - Crash, print, fly again.
- **Learning** - Understand design, aerodynamics, engineering.
- **Repair-friendly** - Print replacement parts on-demand.

**Beginner-Friendly Guides**
- [How to Build an Insanely Cheap 3D Printed FPV Drone](https://www.youtube.com/watch?v=P5DNtCFhqwc) - BinCrafts tutorial on budget builds.
- [3D Printed FPV Drone DIY Guide - Unionfab](https://www.unionfab.com/blog/2024/09/3d-printed-fpv-drone) - Comprehensive design and assembly guide.
- [How to Build a 3D Printed Micro Drone](https://blog.prusa3d.com/how-to-build-a-3d-printed-micro-drone_29310/) - Prusa's 90mm whoop tutorial.
- [How to Build a 3D Printed Drone - Formlabs](https://formlabs.com/white-papers/how-to-build-a-3d-printed-drone/) - Advanced tactical-ready drone guide.

**Recommended Materials**
- **PLA** - Rigid, easy to print, good for main frame.
- **TPU (Flexible)** - Shock absorption, motor mounts, camera mounts.
- **PETG** - Balanced strength and flexibility.
- **Carbon Fiber PLA** - Extra rigidity, higher strength.

**Recommended Printers**
- **Creality Ender 3 V2 Neo** ($200-250) - Best budget option.
- **Prusa i3 MK3S+** ($800+) - Best print quality, auto-leveling.
- **Bambu Lab X1C** ($1,200+) - Fastest, multi-color, advanced features.

**Design Resources**
- [Thingiverse - FPV Drone Frames](https://www.thingiverse.com/search?q=fpv+drone+frame) - Free STL files.
- [Printables - FPV Category](https://www.printables.com/) - Prusa's model repository.
- [Cults3D - Drone Models](https://cults3d.com/) - Premium and free designs.

**Design Your Own**
- **Fusion 360** - Industry-standard CAD (free for hobbyists).
- Focus on X-frame or H-frame designs.
- Ensure motor/propeller clearance.
- Add mounting points for FC, camera, battery.
- Include vibration dampening features.

## Essential Components

### Frame
- **Size**: 3" (micro), 5" (standard), 7" (long-range).
- **Material**: Carbon fiber (commercial) or 3D printed.
- **Weight**: Sub-250g for no FAA registration (US).

### Motors
- **KV Rating**: Higher KV = faster, less torque.
- **Common**: 1404-1408 (3"), 2206-2306 (5").
- **Compatibility**: Match to battery voltage (4S/6S).

### Flight Controller (FC)
- **Features**: Gyro, accelerometer, OSD.
- **Popular**: SpeedyBee, Mamba, Kakute.
- **All-in-One**: FC + ESC combo simplifies wiring.

### Electronic Speed Controllers (ESC)
- **Rating**: Must handle motor current draw.
- **Common**: 35A-45A per motor (5").
- **Protocols**: BlHeli_32, BlHeli_S.

### Video System
- **Analog**: Cheaper ($50-100), lower latency. Camera: Caddx Ratel 2, RunCam Phoenix 2. VTX: 25-600mW adjustable.
- **Digital**: HD quality, higher cost ($200-500). DJI O3/O4 Air Unit. Walksnail Avatar HD.

### Radio Controller
- **Protocols**: ELRS (best range), TBS Crossfire, Frsky.
- **Beginner**: RadioMaster Zorro, BetaFPV LiteRadio 3.
- **Advanced**: RadioMaster TX16S, Radiomaster Pocket.

### FPV Goggles
- **Analog**: Eachine EV800D ($80-120).
- **Digital**: DJI Goggles 2 ($400-600), Skyzone Sky04X.
- **Features**: DVR recording, diversity receivers.

### Batteries
- **Type**: LiPo (Lithium Polymer).
- **Voltage**: 4S (14.8V) or 6S (22.2V).
- **Capacity**: 850-1500mAh (5").
- **C-Rating**: 75C minimum.
- **Safety**: Fireproof charging bag, never over-discharge.

## FPV Software & Configuration

**Flight Controller Firmware**
- [Betaflight](https://betaflight.com/) - Most popular, excellent tuning.
- [Betaflight Configurator](https://github.com/betaflight/betaflight-configurator#readme) - GUI configuration tool.
- [INAV](https://github.com/iNavFlight/inav#readme) - Fixed-wing and GPS waypoint missions.
- [EmuFlight](https://github.com/emuflight/EmuFlight#readme) - Betaflight fork with alternative filters.

**Simulators** (Practice Before Flying!)
- **Liftoff** ($20) - Most realistic physics.
- **DRL Simulator** ($20) - Official racing league sim.
- **Velocidrone** ($20) - Excellent tracks and physics.
- **Uncrashed** (Free) - Budget-friendly option.
- **FPV SkyDive** ($10) - Good for beginners.

**Configuration**
- Display battery voltage, flight time, GPS via OSD.
- Customize warnings and alerts.
- PID tuning for smooth flight.
- Rates/expo for stick feel.
- Filters to reduce noise.
- Blackbox logging for analysis.

## FPV Communities

- [r/fpv](https://www.reddit.com/r/fpv/) - Active Reddit community with 200k+ members.
- [r/Multicopter](https://www.reddit.com/r/Multicopter/) - General drone building.
- [FPV Discord Servers](https://discord.com/) - Real-time help and troubleshooting.
- [Joshua Bardwell YouTube Community](https://www.youtube.com/joshuabardwell) - 500k+ subscribers.
- [Oscar Liang Blog](https://oscarliang.com/) - Comprehensive guides and reviews.
- [IntFPV Discord](https://discord.gg/intfpv) - International FPV community.
- [GetFPV Community](https://www.getfpv.com/learn/) - Tutorials and forums.

## FPV Tutorials & Build Guides

**Step-by-Step Build Tutorials**
- [How to Build an FPV Drone from Scratch (DJI O4)](https://oscarliang.com/how-to-build-fpv-drone/) - Oscar Liang's comprehensive tutorial.
- [How to Build a 5-Inch FPV Racing Drone (2026)](https://www.mepsking.shop/blog/how-to-build-a-5-inch-fpv-racing-drone.html) - DIY guide with parts list and tuning.
- [Beginner's Guide: How to Build Your First FPV Drone](https://www.caddxfpv.com/blogs/news/beginner-s-guide-how-to-build-your-first-fpv-drone) - Component overview and assembly.

**Soldering Guides**
- [Soldering for FPV - Beginners](https://oscarliang.com/soldering-fpv-quadcopter/) - Essential skills tutorial. Practice on old electronics first. Use quality flux and 60/40 rosin-core solder. 350-400°C iron temperature.

**Configuration & Setup**
- [Betaflight Setup Guide](https://oscarliang.com/betaflight/) - Complete configurator walkthrough.
- [ELRS Setup Guide](https://www.expresslrs.org/quick-start/getting-started/) - Long-range control system.
- [OSD Setup Tutorial](https://oscarliang.com/betaflight-osd/) - On-screen display configuration.

**Maintenance & Troubleshooting**
- [Motor Troubleshooting](https://oscarliang.com/quad-motor-propeller-noise/) - Vibration and noise issues.
- [ESC Calibration](https://oscarliang.com/esc-calibration/) - Throttle range setup.
- [Blackbox Analysis](https://oscarliang.com/betaflight-blackbox/) - Flight data review.

## Contributing

Contributions are welcome! Please follow these guidelines:

1. **Fork** this repository.
2. Add your resource with a **clear description**.
3. Ensure links are **beginner-friendly**.
4. Follow the existing **format and structure**.
5. Submit a **pull request**.

### Contribution Criteria
- Resource must be accessible to beginners.
- Links must be working and up-to-date.
- Include brief description of what learners will gain.
- Prefer free resources when available.
- For hardware, include approximate pricing.

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, Evan Kirstein has waived all copyright and related or neighboring rights to this work.

## Acknowledgments

This repository is inspired by:
- [awesome-lora-lorawan](https://github.com/mcicolella/awesome-lora-lorawan#readme) by Mauro Cicolella.
- The Meshtastic community.
- FPV pilots and builders worldwide.

**Disclaimer**: This guide is for educational purposes. Always follow local regulations for radio frequencies and drone flight. FPV flying carries inherent risks - practice in simulators first and fly safely.

---

**Last Updated**: February 2026