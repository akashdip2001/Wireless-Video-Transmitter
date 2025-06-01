# 🔧 **Project Title:** 🟢 `Wireless Video Transmitter Design`

**Non-Invasive Wireless Video Transmitter for Legacy Displays Using RF Signal Injection**

---

## 🧠 **Project Concept:**

Design and develop a **non-contact video transmitter** that sends images or text wirelessly to **existing displays** (e.g., dot matrix, LED boards, or older TV screens) **without any wiring or modification**. It operates by **spoofing or injecting RF signals** that the display already uses — allowing content to appear as if “by magic.”

---

## ✅ **Project Goals:**

* Achieve **display takeover without physical access**
* Use **wireless communication** to send images/text
* Ensure **compatibility with legacy or public signage systems**
* Build a **safe, legal, and portable prototype** suitable for college demonstrations
* Focus on **practicality, innovation, and technical skill application**

---

## 🔍 **Project Approaches Considered**

### ❌ **1. HDMI Dongle with Wireless Video Feed**

**Concept:**
Use a dongle that plugs into the HDMI/AV port of any screen, receiving video from a phone or microcontroller via Wi-Fi or Bluetooth.

**Overview:**
Use an HDMI or AV dongle that plugs into a display and receives video content wirelessly from a phone.

**How It Works:**

* A microcontroller or Raspberry Pi sends video to the dongle
* Mobile phone connects via Wi-Fi Direct or Bluetooth

**Technologies:**

* Protocols: Miracast, DLNA, AirPlay, Wi-Fi Display
* Hardware: Raspberry Pi / ESP32 + HDMI shield

**Innovation:**

* Build a **universal adapter** that supports different display types (HDMI, AV)
* Simplify setup by removing the need for network pairing

**Use Case:**
Like Chromecast, but open-source and customizable.

**Limitations:**

* Requires **physical access** to the display
* **Modern displays already have casting support** (Chromecast, Miracast, etc.)
* Offers **no innovation** beyond existing consumer tech
* Not suitable for **public displays** where ports may be inaccessible

---

### ❌ **2. Analog RF Video Broadcasting (TV Hijack)**

**Concept:**
Transmit modulated analog signals over RF to simulate a TV channel that a display can tune into.

**Overview:**
Transmit analog video over RF to trick old displays (with tuners) into showing your video as a new “TV channel.”

**How It Works:**

* Encode video as NTSC/PAL
* Modulate signal and broadcast it via RF

**Challenges:**

* Legal: RF broadcasting is regulated
* Technical: Only works with displays having analog tuners

**Tools:**

* Raspberry Pi + SDR transmitter
* Analog video encoder module

**Use Case:**
Great for retro setups or closed demo environments.

**Limitations:**

* Only works on **analog displays with RF tuners**
* **Modern displays** are digital-only (HDMI, DVI, DisplayPort)
* RF broadcasting is **heavily regulated** (requires licenses)
* Setup is **complex and outdated**

---

### ✅ **3. RF Spoofing / Wireless Signal Injection (Chosen Approach)**

**Concept:**
Intercept or emulate the **control signals** sent to legacy displays (e.g., dot matrix or LED boards) and transmit your own data using RF or wireless communication.

**Why This Is the Best Option:**

* Targets **legacy public displays** (like those in buses, stations, etc.)
* These displays often receive **simple unencrypted RF or serial signals**
* You can **reverse-engineer the protocol** and inject your own content
* **No need to access the display physically**
* Highly **educational**: involves electronics, embedded systems, and protocol analysis

---

## ⚙️ **Implementation Plan:**

### 1. **Signal Analysis**

* Use an **RTL-SDR**, **HackRF**, or **Flipper Zero** to sniff signals sent to the display
* Determine **frequency**, **modulation type**, and **data protocol**

### 2. **Protocol Decoding**

* Analyze command structure (e.g., ASCII, hex packets)
* Recreate message formats used by original controller

### 3. **Transmission**

* Use an **ESP32 with RF module** or **HackRF** to transmit the same protocol
* Send your own messages (e.g., "WELCOME", or display custom animations/text)

### 4. **Mobile Interface**

* Create a **mobile app or web interface** to control the transmitter
* Send pre-defined or live content from your phone

---

## 🧰 **Key Components:**

| Component                       | Purpose                             |
| ------------------------------- | ----------------------------------- |
| ESP32 or STM32                  | Core controller (Wi-Fi + UART/GPIO) |
| 433 MHz / 868 MHz RF Module     | To transmit spoofed signals         |
| RTL-SDR / HackRF / Flipper Zero | To analyze original signals         |
| Raspberry Pi (optional)         | For complex control logic or UI     |
| Mobile App / Web Interface      | For user control                    |
| Battery Pack                    | For portability                     |

---

## 📘 **Required Skills:**

* Embedded systems (ESP32, microcontrollers)
* RF communication basics (AM/FM modulation, signal injection)
* Signal analysis (SDR tools, waveform decoding)
* Mobile or web development (basic UI to control transmitter)
* Electronics and prototyping

---

## 📏 **Feasibility & Legality:**

* ✅ **Feasible** in a college lab with proper permissions
* ❗ **Do not use** on live public displays without authorization
* Legal if used **within a shielded environment** or using **license-free RF bands**
* Perfect for demonstrating **signal spoofing and wireless injection techniques**

---

## ✅ **Conclusion: Why RF Spoofing Is the Best Path**

| Approach                | Requires Physical Access | Works with Legacy Displays | Legality    | Innovation Level | Feasibility |
| ----------------------- | ------------------------ | -------------------------- | ----------- | ---------------- | ----------- |
| HDMI Dongle             | ✅ Yes                    | ❌ No                       | ✅ Legal     | ❌ Low            | ✅ High      |
| Analog RF Broadcast     | ❌ No                     | ✅ Yes (old TVs)            | ❌ Regulated | ⚠️ Medium        | ❌ Low       |
| **RF Signal Injection** | ❌ No                     | ✅ Yes                      | ✅ With care | ✅ High           | ✅ High      |

**RF spoofing** offers a **safe, innovative, and technically challenging** solution that stands out academically and practically. It applies embedded systems, wireless protocols, and reverse engineering, making it ideal for a student project in electronics or mechatronics.

