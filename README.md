# 🟢 Wireless Video Transmitter Design

If any display **similar old railway station displays** (like dot matrix, segment-based, or early LED panels), then [`Option 2`]() — **RF spoofing or wireless signal injection** — could be a best option.

---

### Why This Project?

* **Old public displays** often receive data through **simple serial protocols** (like RS-232 or RS-485) or **modulated RF**.
* These signals are **not encrypted** and **often broadcasted or wired in a straightforward way**, making them easier to **emulate or spoof**.
* You can build a **custom transmitter** (like with an **ESP32**, **Raspberry Pi**, or **SDR transmitter**) that **mimics the controller** sending commands to the display.
* If the display is truly **RF-controlled**, you could **reverse-engineer the protocol** and **inject your own data**, making the display show what you want.

---

### What We’ll Need to Do?

#### 1. **Study the Display**

* Try to find **where the original content comes from** — is there a control box nearby?
* Does the display update over **RF**, **wired serial**, or **network**?
* If possible, **sniff the signals** using a logic analyzer or **SDR (Software Defined Radio)**.

#### 2. **Capture the Protocol**

* If RF-based: use an **SDR tool like HackRF, RTL-SDR**, or **Flipper Zero** to listen to the frequencies when the display updates.
* If wired: use a **serial sniffer** (e.g., connect to the cable and log data).

#### 3. **Build a Wireless Transmitter**

* Use something like **ESP32 + 433 MHz/868 MHz/2.4 GHz RF module** (depending on what frequency the display uses).
* Reproduce the protocol and send the same type of data with **your own images or text**.

#### 4. **Control It from Your Phone**

* Set up the ESP32 or Pi as a **Wi-Fi hotspot or Bluetooth receiver**.
* Build a simple **mobile app or webpage** that sends commands to your transmitter.

---

### Tools & Components We Might Use:

| Component                          | Use                                     |
| ---------------------------------- | --------------------------------------- |
| ESP32                              | Core controller with Wi-Fi & Bluetooth  |
| RF Transmitter (433 MHz / 2.4 GHz) | To send signals                         |
| RTL-SDR / HackRF                   | For signal analysis and sniffing        |
| Raspberry Pi                       | (optional) for more advanced UI/backend |
| Logic analyzer                     | For capturing wired serial protocols    |
| Battery or power pack              | Portable transmitter                    |
| Basic Android App / Web server     | For sending images/text to display      |

---

### Legal Note for EveryOne:

* **Don’t use this on live public displays** — that can be illegal.
* Since it’s **inside your area** and for a **controlled demo**, it should be fine **with proper permission**.

---
