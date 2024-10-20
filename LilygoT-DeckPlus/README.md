<P align="center"> - <A HREF="https://www.qrz.com/db/WA9ONY">WA9ONY</A> - <A HREF="https://www.youtube.com/user/DavidAHaworth">YouTube</A> - <A HREF="http://www.stargazing.net/david/index.html">Website</A> -<BR>
- LoRa GitHub Repositories: 
<A HREF="https://github.com/WA9ONY/LoRa">LoRa</A> - 
<A HREF="https://github.com/WA9ONY/LoRa/blob/main/Meshtastic/README.md">Meshtastic</A> -
<A HREF="https://github.com/WA9ONY/LoRa/blob/main/LilygoT-DeckPlus/README.md">T-Deck Plus</A> -
<A HREF="https://github.com/WA9ONY/LoRa/blob/main/LilygoT-Echo/README.md">T-Echo</A> -
</P>  
<p align="center">
       <img width="360" height="640" src="/LilygoT-DeckPlus/Images/T-DeckPlus.jpeg">
</p>

# Lilygo T-Deck Plus LoRa Meshtastic Radio

<HR>

Thank you for pointing that out! You're right. Let me correct the errors in the description.

### Corrected Overview of the Lilygo T-Deck Plus LoRa Meshtastic Radio

The **Lilygo T-Deck Plus** is a versatile development board incorporating LoRa (Long Range) wireless communication and designed for use with the **Meshtastic** mesh networking protocol. It is equipped with a variety of features, making it ideal for IoT, communication, and sensor network applications.

#### Corrected Key Features:

1. **LoRa Communication Module**:
   - The T-Deck Plus uses the **Semtech SX1262** LoRa module for long-range, low-power wireless communication. LoRa operates in the unlicensed ISM bands (typically 433 MHz, 868 MHz, or 915 MHz depending on the region).
   - LoRa technology enables communication over several kilometers, which is ideal for remote sensors and devices where low power consumption and long-range communication are essential.

2. **Meshtastic Compatibility**:
   - The board is compatible with the **Meshtastic** open-source firmware, allowing it to participate in mesh networks for peer-to-peer, decentralized communication. This is especially useful for areas with no cellular coverage, or for off-grid applications like outdoor exploration or emergency communications.
   - The mesh network expands as more nodes are added, allowing wide coverage.

3. **ESP32 Processor**:
   - The device is powered by the **ESP32** microcontroller, featuring a dual-core 240 MHz processor, Wi-Fi, Bluetooth, and a wide range of GPIOs for peripherals.
   - The ESP32 platform supports a variety of development environments such as **Arduino**, **PlatformIO**, and **ESP-IDF**, making it easy to program and expand functionality.

4. **Display**:
   - The **T-Deck Plus** comes with a **TFT LCD display** (not an e-paper display). The display allows users to view messages, status information, or other outputs from the board. 
   - Unlike e-paper displays, this TFT display provides faster refresh rates, making it more suitable for real-time information, though at the cost of slightly higher power consumption.

5. **Built-in Keyboard**:
   - One of the standout features of the **T-Deck Plus** is its **built-in mechanical keyboard**. This small keyboard allows for text input, making it easy to send messages or interact with the device, especially when running Meshtastic or other communication protocols.
   - The keyboard enhances usability for scenarios where a user might want to input data directly without needing an external interface or computer.

6. **Power Supply and Management**:
   - The board supports **LiPo batteries** and has an on-board charging circuit, making it portable and ideal for field use. It also features a USB-C port for power and charging.
   - It includes sleep modes to extend battery life, making it suited for long-term, off-grid projects.

7. **Expansion Capabilities**:
   - The board offers multiple GPIO pins for connecting sensors, actuators, and other external devices. It supports **I2C, SPI, and UART** protocols for interfacing with additional components, extending its functionality.
   - This makes it a great choice for environmental monitoring, remote sensing, and other IoT applications.

8. **Antenna and Range**:
   - The LoRa module features a **U.FL connector** for attaching an external LoRa antenna, ensuring maximum signal strength and communication range.
   - Under ideal conditions, the LoRa module can achieve a range of several kilometers, though actual range depends on factors like antenna quality, terrain, and environmental interference.

#### Applications:

- **Off-grid Communication**: With Meshtastic, the T-Deck Plus can be used for communication in remote areas, emergencies, or outdoor adventures where there's no cellular signal.
- **IoT Sensor Networks**: The long-range capabilities of LoRa make it ideal for IoT applications involving distributed sensor networks.
- **Portable Messaging**: The built-in keyboard allows users to communicate or send messages easily in a Meshtastic network.
- **Environmental Monitoring**: The device can be equipped with sensors for remote monitoring of environmental conditions over long distances.

#### Conclusion:
The **Lilygo T-Deck Plus LoRa Meshtastic Radio** combines the power of an ESP32 with LoRa and Meshtastic networking, along with a TFT display and built-in keyboard for versatile communication and control. Its built-in keyboard and long-range communication capabilities make it an excellent choice for field communication, sensor networks, and portable IoT applications.

These corrections should better represent the device’s features. Thanks again for the heads-up!


<HR>

## Links

Stores
+ [Lilygo T-Deck Plus](https://www.lilygo.cc/products/t-deck-plus?bg_ref=xknMV5FzPY)

YouTube Andy Kirby in UK
+ [WAS THIS FANCY MESHTASTIC FIRMWARE DELETED?!](https://youtu.be/Xo8VhT1_VwM?si=sUDfjNN-eIbQilxM)
+ [CREATE A CELL NETWORK FOR SMS IN YOUR TOWN!!!](https://youtu.be/-JJK7gG_N2A?si=BSc6X5BUXIqTXSuy)

Meshtastic Store
+ [mpowered247 in the UK](https://mpowered247.com/)

GitHub
+ [T-Deck](https://github.com/Xinyuan-LilyGO/T-Deck)
  + T-Deck-Plus has assigned the pins on the Grove interface to the GPS module, so the Grove interface of T-Deck-Plus cannot be used.
 



<HR>

## Operating

Right slide switch is the power switch
Left push button is rest/boot

Came with Meshtastic FW V 2.5.1

Takes a while to boot up

Text interface, not the GUI

Node name Meshtastic_5390

Bluebooth interface active

Return sends a message

Display is a touch screen. Swip left or right to move through the bottom dots displays.

[Keyboard Shortcuts](https://meshtastic.org/docs/hardware/devices/lilygo/tdeck/)

Built in speaker alerts when receiving a message.

Type on the keyboard to start entering a message.


