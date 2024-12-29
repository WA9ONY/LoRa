<P align="center"> - <A HREF="https://www.qrz.com/db/WA9ONY">WA9ONY</A> - <A HREF="https://www.youtube.com/user/DavidAHaworth">YouTube</A> - <A HREF="http://www.stargazing.net/david/index.html">Website</A> -<BR>
- LoRa GitHub Repositories: 
<A HREF="https://github.com/WA9ONY/LoRa">LoRa</A> - 
<A HREF="https://github.com/WA9ONY/LoRa/blob/main/Meshtastic/README.md">Meshtastic</A> -
<A HREF="https://github.com/WA9ONY/LoRa/blob/main/LilygoT-DeckPlus/README.md">T-Deck Plus</A> -
<A HREF="https://github.com/WA9ONY/LoRa/blob/main/LilygoT-Echo/README.md">T-Echo</A> -
</P>  

<p align="center">
<img width="896" height="512" src="/Meshtastic_CLI/Images/RPiCLImeshtastic.png">
</p>

<p align="center">
Above is a place holder image by ChatGPT 4o until a real photo is available.
</p>

# LoRa Meshtastic CLI Control of the T-Echo

This page provides information on controlling the Lilygo T-Echo LoRa Meshtastic radio with a Raspberry Pi computer using the Linux terminal CLI (Command Line Interface) and the USB connection between the radio and computer.


<HR>

# Introduction to the [LoRa](https://en.wikipedia.org/wiki/LoRa) [Meshtastic](https://en.wikipedia.org/wiki/Meshtastic) [CLI](https://en.wikipedia.org/wiki/Command-line_interface) Tool

The LoRa Meshtastic CLI tool is a powerful command-line interface designed to configure, monitor, and interact with Meshtastic devices. Meshtastic is an open-source project that leverages LoRa (Long Range) communication technology to create low-power, long-distance mesh networks, which are particularly useful for scenarios where conventional connectivity (Wi-Fi, cellular) is unavailable or unreliable.

The CLI tool allows users to access and control the Meshtastic device's functionalities without relying on graphical interfaces. This flexibility is ideal for developers, tinkerers, and advanced users who need to script, automate, or perform detailed customizations.

The Meshtastic CLI tool is essential for:

+ Configuration: Customize device settings such as channel parameters, power levels, and region-specific options.
+ Network Management: Monitor network traffic, view connected nodes, and troubleshoot issues.
+ Scripting and Automation: Automate tasks like firmware updates, mass configuration, or logging.
+ Debugging: Access detailed logs and device information for diagnosing network problems.
+ Advanced Features: Explore and enable experimental or less frequently used features.


<HR>

# Raspberry Pi Computer

The following CLI command provides information about the Raspberry Pi computer.
```bash

david@raspberrypi5:~ $ neofetch
       _,met$$$$$gg.          david@raspberrypi5 
    ,g$$$$$$$$$$$$$$$P.       ------------------ 
  ,g$$P"     """Y$$.".        OS: Debian GNU/Linux 12 (bookworm) aarch64 
 ,$$P'              `$$$.     Host: Raspberry Pi 5 Model B Rev 1.0 
',$$P       ,ggs.     `$$b:   Kernel: 6.6.62+rpt-rpi-2712 
`d$$'     ,$P"'   .    $$$    Uptime: 4 hours, 38 mins 
 $$P      d$'     ,    $$P    Packages: 1613 (dpkg) 
 $$:      $$.   -    ,d$$'    Shell: bash 5.2.15 
 $$;      Y$b._   _,d$P'      Resolution: 1920x1080 
 Y$$.    `.`"Y$$$$P"'         DE: labwc:wlroots 
 `$$b      "-.__              Theme: PiXflat [GTK3] 
  `Y$$                        Icons: PiXflat [GTK3] 
   `Y$$.                      Terminal: lxterminal 
     `$$b.                    Terminal Font: Monospace 10 
       `Y$$b.                 CPU: (4) @ 2.400GHz 
          `"Y$b._             Memory: 1117MiB / 8048MiB 
              `"""
                                                      
                                                      


david@raspberrypi5:~ $ 
```

<HR>

# Meshtastic CLI Command

The following CLI command provides information about the meshtastic CLI command.

CLI meshtastic and meshtastic -h both display meshtastic help information.

```bash

david@raspberrypi5:~ $ meshtastic
usage: meshtastic [-h | --version | --support] [--port [PORT] | --host [HOST]
                  | --ble [BLE]] [--ble-scan] [--dest !xxxxxxxx]
                  [--ch-index INDEX] [--configure CONFIGURE] [--export-config]
                  [--get FIELD] [--set FIELD VALUE] [--begin-edit]
                  [--commit-edit] [--get-canned-message]
                  [--set-canned-message SET_CANNED_MESSAGE] [--get-ringtone]
                  [--set-ringtone RINGTONE] [--ch-vlongslow] [--ch-longslow]
                  [--ch-longfast] [--ch-medslow] [--ch-medfast]
                  [--ch-shortslow] [--ch-shortfast] [--set-owner SET_OWNER]
                  [--set-owner-short SET_OWNER_SHORT] [--set-ham SET_HAM]
                  [--seturl SETURL] [--setalt SETALT] [--setlat SETLAT]
                  [--setlon SETLON] [--remove-position]
                  [--pos-fields [POS_FIELDS ...]] [--ch-add CH_ADD] [--ch-del]
                  [--ch-set FIELD VALUE] [--channel-fetch-attempts ATTEMPTS]
                  [--qr] [--qr-all] [--ch-enable] [--ch-disable] [--info]
                  [--nodes] [--sendtext TEXT] [--traceroute !xxxxxxxx]
                  [--request-telemetry [TYPE]] [--request-position] [--reply]
                  [--reboot | --reboot-ota | --enter-dfu | --shutdown | --device-metadata | --factory-reset | --factory-reset-device | --remove-node !xxxxxxxx | --reset-nodedb | --set-time [TIMESTAMP]]
                  [--seriallog [LOG_DESTINATION]] [--ack] [--timeout SECONDS]
                  [--no-nodes] [--debug] [--test]
                  [--wait-to-disconnect [SECONDS]] [--noproto] [--listen]
                  [--no-time]
                  [--power-riden POWER_RIDEN | --power-ppk2-meter | --power-ppk2-supply | --power-sim]
                  [--power-voltage POWER_VOLTAGE] [--power-stress]
                  [--power-wait] [--slog [SLOG]]
                  [--gpio-wrb GPIO_WRB GPIO_WRB] [--gpio-rd GPIO_RD]
                  [--gpio-watch GPIO_WATCH] [--tunnel] [--subnet TUNNEL_NET]

Help:
  -h, --help            show this help message and exit
  --version             show program's version number and exit
  --support             Show support info (useful when troubleshooting an
                        issue)

Connection:
  Optional arguments that specify how to connect to a Meshtastic device.

  --port [PORT], --serial [PORT], -s [PORT]
                        The port of the device to connect to using serial,
                        e.g. /dev/ttyUSB0. (defaults to trying to detect a
                        port)
  --host [HOST], --tcp [HOST], -t [HOST]
                        Connect to a device using TCP, optionally passing
                        hostname or IP address to use. (defaults to
                        'localhost')
  --ble [BLE], -b [BLE]
                        Connect to a BLE device, optionally specifying a
                        device name (defaults to 'any')
  --ble-scan            Scan for Meshtastic BLE devices that may be available
                        to connect to

Selection:
  Arguments that select channels to use, destination nodes, etc.

  --dest !xxxxxxxx      The destination node id for any sent commands, if not
                        set '^all' or '^local' is assumed as appropriate
  --ch-index INDEX      Set the specified channel index for channel-specific
                        commands. Channels start at 0 (0 is the PRIMARY
                        channel).

Import/Export:
  Arguments that concern importing and exporting configuration of Meshtastic
  devices

  --configure CONFIGURE
                        Specify a path to a yaml(.yml) file containing the
                        desired settings for the connected device.
  --export-config       Export the configuration in yaml(.yml) format.

Configuration:
  Arguments that concern general configuration of Meshtastic devices

  --get FIELD           Get a preferences field. Use an invalid field such as
                        '0' to get a list of all fields. Can use either
                        snake_case or camelCase format. (ex: 'ls_secs' or
                        'lsSecs')
  --set FIELD VALUE     Set a preferences field. Can use either snake_case or
                        camelCase format. (ex: 'ls_secs' or 'lsSecs')
  --begin-edit          Tell the node to open a transaction to edit settings
  --commit-edit         Tell the node to commit open settings transaction
  --get-canned-message  Show the canned message plugin message
  --set-canned-message SET_CANNED_MESSAGE
                        Set the canned messages plugin message (up to 200
                        characters).
  --get-ringtone        Show the stored ringtone
  --set-ringtone RINGTONE
                        Set the Notification Ringtone (up to 230 characters).
  --ch-vlongslow        Change to the very long-range and slow modem preset
  --ch-longslow         Change to the long-range and slow modem preset
  --ch-longfast         Change to the long-range and fast modem preset
  --ch-medslow          Change to the med-range and slow modem preset
  --ch-medfast          Change to the med-range and fast modem preset
  --ch-shortslow        Change to the short-range and slow modem preset
  --ch-shortfast        Change to the short-range and fast modem preset
  --set-owner SET_OWNER
                        Set device owner name
  --set-owner-short SET_OWNER_SHORT
                        Set device owner short name
  --set-ham SET_HAM     Set licensed Ham ID and turn off encryption
  --seturl SETURL       Set a channel URL

Position Configuration:
  Arguments that modify fixed position and other position-related
  configuration.

  --setalt SETALT       Set device altitude in meters (allows use without
                        GPS), and enable fixed position. When providing
                        positions with `--setlat`, `--setlon`, and `--setalt`,
                        missing values will be set to 0.
  --setlat SETLAT       Set device latitude (allows use without GPS), and
                        enable fixed position. Accepts a decimal value or an
                        integer premultiplied by 1e7. When providing positions
                        with `--setlat`, `--setlon`, and `--setalt`, missing
                        values will be set to 0.
  --setlon SETLON       Set device longitude (allows use without GPS), and
                        enable fixed position. Accepts a decimal value or an
                        integer premultiplied by 1e7. When providing positions
                        with `--setlat`, `--setlon`, and `--setalt`, missing
                        values will be set to 0.
  --remove-position     Clear any existing fixed position and disable fixed
                        position.
  --pos-fields [POS_FIELDS ...]
                        Specify fields to send when sending a position. Use no
                        argument for a list of valid values. Can pass multiple
                        values as a space separated list like this: '--pos-
                        fields ALTITUDE HEADING SPEED'

Channel Configuration:
  Arguments that concern configuration of channels

  --ch-add CH_ADD       Add a secondary channel, you must specify a channel
                        name
  --ch-del              Delete the ch-index channel
  --ch-set FIELD VALUE  Set a channel parameter. To see channel settings
                        available:'--ch-set all all --ch-index 0'. Can set the
                        'psk' using this command. To disable encryption on
                        primary channel:'--ch-set psk none --ch-index 0'. To
                        set encryption with a new random key on second
                        channel:'--ch-set psk random --ch-index 1'. To set
                        encryption back to the default:'--ch-set psk default
                        --ch-index 0'. To set encryption with your own key: '
                        --ch-set psk 0x1a1a1a1a2b2b2b2b1a1a1a1a2b2b2b2b1a1a1a1
                        a2b2b2b2b1a1a1a1a2b2b2b2b --ch-index 0'.
  --channel-fetch-attempts ATTEMPTS
                        Attempt to retrieve channel settings for --ch-set this
                        many times before giving up. Default 3.
  --qr                  Display a QR code for the node's primary channel (or
                        all channels with --qr-all). Also shows the shareable
                        channel URL.
  --qr-all              Display a QR code and URL for all of the node's
                        channels.
  --ch-enable           Enable the specified channel. Use --ch-add instead
                        whenever possible.
  --ch-disable          Disable the specified channel Use --ch-del instead
                        whenever possible.

Local Actions:
  Arguments that take actions or request information from the local node
  only.

  --info                Read and display the radio config information
  --nodes               Print Node List in a pretty formatted table

Remote Actions:
  Arguments that take actions or request information from either the local
  node or remote nodes via the mesh.

  --sendtext TEXT       Send a text message. Can specify a destination '--
                        dest' and/or channel index '--ch-index'.
  --traceroute !xxxxxxxx
                        Traceroute from connected node to a destination. You
                        need pass the destination ID as argument, like this: '
                        --traceroute !ba4bf9d0' Only nodes with a shared
                        channel can be traced.
  --request-telemetry [TYPE]
                        Request telemetry from a node. With an argument,
                        requests that specific type of telemetry. You need to
                        pass the destination ID as argument with '--dest'. For
                        repeaters, the nodeNum is required.
  --request-position    Request the position from a node. You need to pass the
                        destination ID as an argument with '--dest'. For
                        repeaters, the nodeNum is required.
  --reply               Reply to received messages

Remote Admin Actions:
  Arguments that interact with local node or remote nodes via the mesh,
  requiring admin access.

  --reboot              Tell the destination node to reboot
  --reboot-ota          Tell the destination node to reboot into factory
                        firmware (ESP32)
  --enter-dfu           Tell the destination node to enter DFU mode (NRF52)
  --shutdown            Tell the destination node to shutdown
  --device-metadata     Get the device metadata from the node
  --factory-reset, --factory-reset-config
                        Tell the destination node to install the default
                        config, preserving BLE bonds & PKI keys
  --factory-reset-device
                        Tell the destination node to install the default
                        config and clear BLE bonds & PKI keys
  --remove-node !xxxxxxxx
                        Tell the destination node to remove a specific node
                        from its DB, by node number or ID
  --reset-nodedb        Tell the destination node to clear its list of nodes
  --set-time [TIMESTAMP]
                        Set the time to the provided unix epoch timestamp, or
                        the system's current time if omitted or 0.

Miscellaneous arguments:
  --seriallog [LOG_DESTINATION]
                        Log device serial output to either 'none' or a
                        filename to append to. Defaults to 'stdout' if no
                        filename specified.
  --ack                 Use in combination with compatible actions (e.g.
                        --sendtext) to wait for an acknowledgment.
  --timeout SECONDS     How long to wait for replies. Default 300s.
  --no-nodes            Request that the node not send node info to the
                        client. Will break things that depend on the nodedb,
                        but will speed up startup. Requires 2.3.11+ firmware.
  --debug               Show API library debug log messages
  --test                Run stress test against all connected Meshtastic
                        devices
  --wait-to-disconnect [SECONDS]
                        How many seconds to wait before disconnecting from the
                        device.
  --noproto             Don't start the API, just function as a dumb serial
                        terminal.
  --listen              Just stay open and listen to the protobuf stream.
                        Enables debug logging.
  --no-time             Deprecated. Retained for backwards compatibility in
                        scripts, but is a no-op.

Power Testing:
  Options for power testing/logging.

  --power-riden POWER_RIDEN
                        Talk to a Riden power-supply. You must specify the
                        device path, i.e. /dev/ttyUSBxxx
  --power-ppk2-meter    Talk to a Nordic Power Profiler Kit 2 (in meter mode)
  --power-ppk2-supply   Talk to a Nordic Power Profiler Kit 2 (in supply mode)
  --power-sim           Use a simulated power meter (for development)
  --power-voltage POWER_VOLTAGE
                        Set the specified voltage on the power-supply. Be VERY
                        careful, you can burn things up.
  --power-stress        Perform power monitor stress testing, to capture a
                        power consumption profile for the device (also
                        requires --power-mon)
  --power-wait          Prompt the user to wait for device reset before
                        looking for device serial ports (some boards kill
                        power to USB serial port)
  --slog [SLOG]         Store structured-logs (slogs) for this run, optionally
                        you can specify a destination directory

Remote Hardware:
  Arguments related to the Remote Hardware module

  --gpio-wrb GPIO_WRB GPIO_WRB
                        Set a particular GPIO # to 1 or 0
  --gpio-rd GPIO_RD     Read from a GPIO mask (ex: '0x10')
  --gpio-watch GPIO_WATCH
                        Start watching a GPIO mask for changes (ex: '0x10')

Tunnel:
  Arguments related to establishing a tunnel device over the mesh.

  --tunnel              Create a TUN tunnel device for forwarding IP packets
                        over the mesh
  --subnet TUNNEL_NET   Sets the local-end subnet address for the TUN IP
                        bridge. (ex: 10.115' which is the default)

If no connection arguments are specified, we search for a compatible serial
device, and if none is found, then attempt a TCP connection to localhost.

david@raspberrypi5:~ $ 

```

<HR>

# Meshtastic CLI Command Version

The following CLI command provides information about the meshtastic CLI command version.

```bash
david@raspberrypi5:~ $ meshtastic --version
2.5.5
david@raspberrypi5:~ $ 

```

<HR>

# Meshtastic CLI Send Text Message

The following CLI command sends a text message.

The Lilygo T-Echo is ttyACM0

```bash
david@raspberrypi5:~ $ meshtastic --port /dev/ttyACM0 --sendtext "Hello from Raspberry Pi 5!"
Connected to radio
Sending text message Hello from Raspberry Pi 5! to ^all on channelIndex:0
david@raspberrypi5:~ $ 

```

<HR>

# Meshtastic CLI Info Message

The following CLI command get information from the Lilygo T-Echo.

The Lilygo T-Echo is ttyACM0

```bash
david@raspberrypi5:~ $ meshtastic --port /dev/ttyACM0 --info
Connected to radio

Owner: WA9ONY-10 (ON10)
My info: { "myNodeNum": 359015253, "minAppVersion": 30200, "rebootCount": 0 }
Metadata: { "firmwareVersion": "2.5.15.79da236", "deviceStateVersion": 23, "canShutdown": true, "hasBluetooth": true, "positionFlags": 811, "hwModel": "T_ECHO", "hasPKC": true, "hasWifi": false, "hasEthernet": false, "role": "CLIENT", "hasRemoteHardware": false }

Nodes in mesh: {
  "!15662355": {
    "num": 359015253,
    "user": {
      "id": "!15662355",
      "longName": "WA9ONY-10",
      "shortName": "ON10",
      "macaddr": "de:ed:15:66:23:55",
      "hwModel": "T_ECHO",
      "publicKey": "5j0wZkhSApxrdD3CeRtABVp5hUcMmcoUkrxnGxucv1k="
    },
    "position": {
      "time": 1735513250
    },
    "lastHeard": 1735513250,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.763,
      "channelUtilization": 26.851665,
      "airUtilTx": 5.1246943,
      "uptimeSeconds": 28291
    },
    "isFavorite": true
  },
  "!da5443d4": {
    "num": 3662955476,
    "user": {
      "id": "!da5443d4",
      "longName": "Mobile Analytic Laboratory Probe",
      "shortName": "MALP",
      "macaddr": "34:b7:da:54:43:d4",
      "hwModel": "HELTEC_V3",
      "publicKey": "dPK5L7pvUx80xna22W4jRkHusU43w2DkcSpVRjXz4yY="
    },
    "position": {
      "latitudeI": 454700000,
      "longitudeI": -1226160000,
      "altitude": 69,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.47,
      "longitude": -122.616
    },
    "snr": 5.75,
    "lastHeard": 1735487889,
    "deviceMetrics": {
      "batteryLevel": 98,
      "voltage": 4.173,
      "channelUtilization": 22.575,
      "airUtilTx": 5.0834723,
      "uptimeSeconds": 25196
    },
    "hopsAway": 2
  },
  "!da5cbacc": {
    "num": 3663510220,
    "user": {
      "id": "!da5cbacc",
      "longName": "R2-D2",
      "shortName": "R2D2",
      "macaddr": "34:b7:da:5c:ba:cc",
      "hwModel": "HELTEC_V3",
      "publicKey": "5sXQQZBN/YnBNBN1SYyc/xoEpfM2jqZFn9PmcC/90FI="
    },
    "snr": 6.75,
    "lastHeard": 1735252690,
    "deviceMetrics": {
      "batteryLevel": 97,
      "voltage": 4.153,
      "channelUtilization": 20.781666,
      "airUtilTx": 6.287472,
      "uptimeSeconds": 1493274
    },
    "hopsAway": 3
  },
  "!4a88b649": {
    "num": 1250473545,
    "user": {
      "id": "!4a88b649",
      "longName": "ALFA",
      "shortName": "ALFA",
      "macaddr": "ea:e1:4a:88:b6:49",
      "hwModel": "T_ECHO",
      "publicKey": "Iv/vmcAvd5xQ2oR4exJULuoFxlEvAzr/7d/pwCUMGWw="
    },
    "position": {
      "latitudeI": 454777461,
      "longitudeI": -1224735253,
      "altitude": 167,
      "time": 1735486304,
      "latitude": 45.4777461,
      "longitude": -122.4735253
    },
    "snr": 6.0,
    "lastHeard": 1735486343,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.932,
      "channelUtilization": 24.906666,
      "airUtilTx": 4.5985,
      "uptimeSeconds": 1142079
    },
    "hopsAway": 3
  },
  "!435613e0": {
    "num": 1129714656,
    "user": {
      "id": "!435613e0",
      "longName": "NET 13e0",
      "shortName": "13e0",
      "macaddr": "48:ca:43:56:13:e0",
      "hwModel": "HELTEC_WIRELESS_PAPER",
      "publicKey": "9GLTZKnz8WLcPY7hW4wT/I4fCabOretQZf0URxZDhGs="
    },
    "position": {
      "latitudeI": 454557696,
      "longitudeI": -1226309632,
      "time": 1735245777,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.4557696,
      "longitude": -122.6309632
    },
    "snr": 6.5,
    "lastHeard": 1735248657,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.222,
      "channelUtilization": 22.111666,
      "airUtilTx": 4.8426666,
      "uptimeSeconds": 90864
    },
    "hopsAway": 3
  },
  "!de2c1f8f": {
    "num": 3727433615,
    "user": {
      "id": "!de2c1f8f",
      "longName": "MultiPASS",
      "shortName": "PASS",
      "macaddr": "f8:d1:de:2c:1f:8f",
      "hwModel": "TRACKER_T1000_E",
      "role": "CLIENT_MUTE",
      "publicKey": "uZbwjUBuepUeVISEE4Z52SB7oHjn/g3RfZjwXgnNpDc="
    },
    "position": {
      "latitudeI": 454705152,
      "longitudeI": -1226129408,
      "altitude": 83,
      "time": 1735489171,
      "latitude": 45.4705152,
      "longitude": -122.6129408
    },
    "snr": 6.5,
    "lastHeard": 1735489178,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.182,
      "channelUtilization": 24.531668,
      "airUtilTx": 0.45777777,
      "uptimeSeconds": 762655
    },
    "hopsAway": 4
  },
  "!533d1420": {
    "num": 1396511776,
    "user": {
      "id": "!533d1420",
      "longName": "Charter Oak 1 - Base",
      "shortName": "RSR1",
      "macaddr": "db:22:53:3d:14:20",
      "hwModel": "RAK4631",
      "role": "CLIENT_MUTE",
      "publicKey": "JcWoEaip236xVE4Sf231KbRtdlpSmch3BIyP8A7COhY="
    },
    "snr": 6.0,
    "lastHeard": 1735485001,
    "deviceMetrics": {
      "batteryLevel": 81,
      "voltage": 3.996,
      "channelUtilization": 9.8949995,
      "airUtilTx": 0.3333889,
      "uptimeSeconds": 3761803
    },
    "hopsAway": 2
  },
  "!fa6bb8c0": {
    "num": 4201363648,
    "user": {
      "id": "!fa6bb8c0",
      "longName": "Shrimp Hel 2",
      "shortName": "SHL2",
      "macaddr": "f4:12:fa:6b:b8:c0",
      "hwModel": "HELTEC_V3",
      "publicKey": "EOYO46gq9Z+LiTzUKgK1/rOED7qeRXyWCCFmxzeimBk="
    },
    "snr": 6.25,
    "lastHeard": 1735488045,
    "deviceMetrics": {
      "batteryLevel": 99,
      "voltage": 4.184,
      "channelUtilization": 11.318334,
      "airUtilTx": 3.8354445,
      "uptimeSeconds": 4659821
    },
    "hopsAway": 5
  },
  "!3b46b8e8": {
    "num": 994490600,
    "user": {
      "id": "!3b46b8e8",
      "longName": "Shrimp Station",
      "shortName": "SHST",
      "macaddr": "ec:da:3b:46:b8:e8",
      "hwModel": "STATION_G2",
      "publicKey": "3ME5h71DSlGGiBoDL25jaH1yS8cbIhHI8ozlYGBb6wI="
    },
    "snr": 6.5,
    "lastHeard": 1735487426,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 0.0,
      "channelUtilization": 19.005001,
      "airUtilTx": 4.8531947,
      "uptimeSeconds": 3578451
    },
    "hopsAway": 3
  },
  "!75f1826c": {
    "num": 1978761836,
    "user": {
      "id": "!75f1826c",
      "longName": "\ud83c\udf32tree_mesh\ud83c\udf32",
      "shortName": "\ud83c\udf32",
      "macaddr": "dc:54:75:f1:82:6c",
      "hwModel": "TLORA_T3_S3",
      "publicKey": "I2kpuwXMlU99fqnwqRPrp7pkQgJxVgi2AEzXck7TYGo="
    },
    "position": {
      "latitudeI": 453771264,
      "longitudeI": -1226571776,
      "altitude": 78,
      "time": 1735250832,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.3771264,
      "longitude": -122.6571776
    },
    "snr": 1.5,
    "lastHeard": 1735252637,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.475,
      "channelUtilization": 22.068333,
      "airUtilTx": 5.7369723,
      "uptimeSeconds": 4556784
    },
    "hopsAway": 2
  },
  "!e433c340": {
    "num": 3828597568,
    "user": {
      "id": "!e433c340",
      "longName": "WhoKnows",
      "shortName": "Who",
      "macaddr": "da:95:e4:33:c3:40",
      "hwModel": "HELTEC_MESH_NODE_T114",
      "publicKey": "OSbD4raRjsunNTYOt9z26Wer2ODOCQ7/wCh1LUd2miw="
    },
    "position": {
      "latitudeI": 456392704,
      "longitudeI": -1224998912,
      "altitude": 62,
      "time": 1735486187,
      "locationSource": "LOC_INTERNAL",
      "latitude": 45.6392704,
      "longitude": -122.4998912
    },
    "snr": 6.75,
    "lastHeard": 1735486868,
    "deviceMetrics": {
      "batteryLevel": 34,
      "voltage": 3.575,
      "channelUtilization": 0.0,
      "airUtilTx": 2.6320279,
      "uptimeSeconds": 67013
    },
    "hopsAway": 2
  },
  "!93879634": {
    "num": 2475136564,
    "user": {
      "id": "!93879634",
      "longName": "Steel Art",
      "shortName": "\ud83d\udd29",
      "macaddr": "44:17:93:87:96:34",
      "hwModel": "TBEAM",
      "publicKey": "UvyZtWGmWUXQtoJv/yrPTbAXh7zNrakviIOlDvVuCm4="
    },
    "snr": 6.25,
    "lastHeard": 1735487785,
    "deviceMetrics": {
      "batteryLevel": 100,
      "voltage": 4.167,
      "channelUtilization": 10.03,
      "airUtilTx": 5.301194,
      "uptimeSeconds": 840053
    },
    "hopsAway": 2
  },
  "!da622714": {
    "num": 3663865620,
    "user": {
      "id": "!da622714",
      "longName": "YCM\ud83c\udfe0",
      "shortName": "YCM6",
      "macaddr": "34:b7:da:62:27:14",
      "hwModel": "HELTEC_V3",
      "publicKey": "PnC/ko7aYMeea+PSclVs1+ODRDteRGQ8TT0q6UmnpUI="
    },
    "position": {
      "latitudeI": 452163066,
      "longitudeI": -1232206680,
      "altitude": 50,
      "time": 1735485609,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.2163066,
      "longitude": -123.220668
    },
    "snr": 4.25,
    "lastHeard": 1735486902,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.205,
      "channelUtilization": 21.206667,
      "airUtilTx": 1.9244443,
      "uptimeSeconds": 783284
    },
    "hopsAway": 6
  },
  "!e1b10237": {
    "num": 3786474039,
    "user": {
      "id": "!e1b10237",
      "longName": "Meshtastic 0237",
      "shortName": "0237",
      "macaddr": "ee:5c:e1:b1:02:37",
      "hwModel": "RAK4631",
      "publicKey": "lBzowhXQ6R1oid6bz+4bX3OVPVekjuE63HFKRVYguR4="
    },
    "snr": 6.0,
    "lastHeard": 1735247853,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.232,
      "channelUtilization": 24.071667,
      "airUtilTx": 2.9359722,
      "uptimeSeconds": 75289
    },
    "hopsAway": 2
  },
  "!93878558": {
    "num": 2475132248,
    "user": {
      "id": "!93878558",
      "longName": "The Jungle",
      "shortName": "TJ",
      "macaddr": "44:17:93:87:85:58",
      "hwModel": "TBEAM",
      "publicKey": "LS/BHvhTj9rKlxaRxXN/zjuvaJDveGLN8qYJ8/LJK3w="
    },
    "snr": 6.0,
    "lastHeard": 1735487841,
    "deviceMetrics": {
      "batteryLevel": 100,
      "voltage": 4.152,
      "channelUtilization": 15.081666,
      "airUtilTx": 5.4431944,
      "uptimeSeconds": 5237760
    },
    "hopsAway": 2
  },
  "!a2e9632c": {
    "num": 2733204268,
    "user": {
      "id": "!a2e9632c",
      "longName": "zoom",
      "shortName": "Z",
      "macaddr": "cc:8d:a2:e9:63:2c",
      "hwModel": "STATION_G2",
      "publicKey": "e7N4Du9PLANoFYjBgi1m8hBEcPnEiMxpDYi048xMb1I="
    },
    "position": {
      "latitudeI": 456392704,
      "longitudeI": -1224998912,
      "altitude": 79,
      "time": 1735181020,
      "locationSource": "LOC_EXTERNAL",
      "latitude": 45.6392704,
      "longitude": -122.4998912
    },
    "snr": 6.0,
    "lastHeard": 1735487379,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 0.0,
      "channelUtilization": 10.5633335,
      "airUtilTx": 3.862167,
      "uptimeSeconds": 199938
    },
    "hopsAway": 1
  },
  "!7c5ccb30": {
    "num": 2086456112,
    "user": {
      "id": "!7c5ccb30",
      "longName": "ROME2",
      "shortName": "ROME",
      "macaddr": "24:58:7c:5c:cb:30",
      "hwModel": "HELTEC_V3",
      "role": "CLIENT_MUTE",
      "publicKey": "pGaOoUXbdlKISReESvhaaeBnFL+ALNeco+WbrOiqEhU="
    },
    "position": {
      "latitudeI": 453771264,
      "longitudeI": -1226047488,
      "altitude": 42,
      "time": 1735249524,
      "latitude": 45.3771264,
      "longitude": -122.6047488
    },
    "snr": 5.5,
    "lastHeard": 1735249542,
    "deviceMetrics": {
      "batteryLevel": 74,
      "voltage": 3.939,
      "channelUtilization": 18.348333,
      "airUtilTx": 0.29922223,
      "uptimeSeconds": 149191
    },
    "hopsAway": 5
  },
  "!9343ba8d": {
    "num": 2470689421,
    "user": {
      "id": "!9343ba8d",
      "longName": "Surprise",
      "shortName": "RUBY",
      "macaddr": "f2:3c:93:43:ba:8d",
      "hwModel": "RAK4631",
      "role": "CLIENT_MUTE",
      "publicKey": "iuljnQbiZxYOTDCJyDOKO7UrR5leeN1ICLq99bn7PjI="
    },
    "position": {
      "latitudeI": 454819840,
      "longitudeI": -1226571776,
      "altitude": 42,
      "time": 1735488443,
      "locationSource": "LOC_INTERNAL",
      "latitude": 45.481984,
      "longitude": -122.6571776
    },
    "snr": 6.5,
    "lastHeard": 1735488451,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.118,
      "channelUtilization": 17.79,
      "airUtilTx": 0.06272222,
      "uptimeSeconds": 8278
    },
    "hopsAway": 2
  },
  "!85895a6c": {
    "num": 2240371308,
    "user": {
      "id": "!85895a6c",
      "longName": "YCM\ud83d\uddfb",
      "shortName": "YCM9",
      "macaddr": "c0:f2:85:89:5a:6c",
      "hwModel": "RAK4631",
      "role": "ROUTER",
      "publicKey": "oN2/awM4K3TkmIxgX2mGBS3v5Mr7USNDc3b8UivPwDw="
    },
    "snr": 6.0,
    "lastHeard": 1735249025,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.128,
      "channelUtilization": 31.54,
      "airUtilTx": 6.6338053,
      "uptimeSeconds": 3004889
    },
    "hopsAway": 5
  },
  "!da5afa6c": {
    "num": 3663395436,
    "user": {
      "id": "!da5afa6c",
      "longName": "gtn",
      "shortName": "gtn",
      "macaddr": "34:b7:da:5a:fa:6c",
      "hwModel": "TLORA_T3_S3",
      "publicKey": "ycLQaR1JDd2CVrxhV5RozEFiMxbTSEn9tAqMGcAqnww="
    },
    "position": {
      "latitudeI": 455114752,
      "longitudeI": -1226866688,
      "time": 1735487601,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.5114752,
      "longitude": -122.6866688
    },
    "snr": 6.25,
    "lastHeard": 1735487638,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.418,
      "channelUtilization": 9.513333,
      "airUtilTx": 4.7376113,
      "uptimeSeconds": 1100135
    },
    "hopsAway": 3
  },
  "!da5487c4": {
    "num": 3662972868,
    "user": {
      "id": "!da5487c4",
      "longName": "NET 87C4",
      "shortName": "87C4",
      "macaddr": "34:b7:da:54:87:c4",
      "hwModel": "HELTEC_V3",
      "publicKey": "s3p9yxOL5DxfPxAUeeezDF6rmXXerEQGZ7B3/Hq7sWU="
    },
    "position": {
      "latitudeI": 454727565,
      "longitudeI": -1225941392,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.4727565,
      "longitude": -122.5941392
    },
    "snr": 5.25,
    "lastHeard": 1735487898,
    "deviceMetrics": {
      "batteryLevel": 100,
      "voltage": 4.195,
      "channelUtilization": 20.868332,
      "airUtilTx": 5.989639,
      "uptimeSeconds": 130206
    },
    "hopsAway": 3
  },
  "!90a0ff04": {
    "num": 2426470148,
    "user": {
      "id": "!90a0ff04",
      "longName": "NET ff04",
      "shortName": "ff04",
      "macaddr": "e8:06:90:a0:ff:04",
      "hwModel": "SEEED_XIAO_S3",
      "publicKey": "Sh6I/jkU7EqnBy1+Sg3KSNvIxxSBeHCGpGFFpeaVWhQ="
    },
    "position": {
      "latitudeI": 454033408,
      "longitudeI": -1225785344,
      "time": 1735278397,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.4033408,
      "longitude": -122.5785344
    },
    "snr": 6.5,
    "lastHeard": 1735278411,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 0.0,
      "channelUtilization": 6.68,
      "airUtilTx": 2.9888055,
      "uptimeSeconds": 7851
    },
    "hopsAway": 3
  },
  "!2a62ddab": {
    "num": 711122347,
    "user": {
      "id": "!2a62ddab",
      "longName": "Meshtastic ddab",
      "shortName": "ddab",
      "macaddr": "eb:1a:2a:62:dd:ab",
      "hwModel": "RAK4631",
      "publicKey": "KK4jLoW7sOM8QwNIJmn6z+hbxAoUWI3GaKRdNn27Sxg="
    },
    "snr": 6.0,
    "lastHeard": 1735488041,
    "deviceMetrics": {
      "batteryLevel": 83,
      "voltage": 4.01,
      "channelUtilization": 15.12,
      "airUtilTx": 4.586889,
      "uptimeSeconds": 323026
    },
    "hopsAway": 5
  },
  "!335c1bd0": {
    "num": 861674448,
    "user": {
      "id": "!335c1bd0",
      "longName": "KAB Antonio Bay\ud83d\ude36\u200d\ud83c\udf2b\ufe0f",
      "shortName": "KAB",
      "macaddr": "64:e8:33:5c:1b:d0",
      "hwModel": "HELTEC_V3",
      "publicKey": "NHU835lRBKCDpBvOfFMpiA5entRe5ztJJVycNhnyfmU="
    },
    "snr": 7.0,
    "lastHeard": 1735278388,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.26,
      "channelUtilization": 22.898333,
      "airUtilTx": 4.27425,
      "uptimeSeconds": 151180
    },
    "hopsAway": 1
  },
  "!33696d74": {
    "num": 862547316,
    "user": {
      "id": "!33696d74",
      "longName": "Showers Pass",
      "shortName": "SP",
      "macaddr": "64:e8:33:69:6d:74",
      "hwModel": "HELTEC_V3",
      "publicKey": "zJ6YoGB0tvZYUw1vVTCtCe48ETptZAF6ONipAX4+8gs="
    },
    "snr": 5.75,
    "lastHeard": 1735487430,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.239,
      "channelUtilization": 12.393333,
      "airUtilTx": 3.403222,
      "uptimeSeconds": 1629723
    },
    "hopsAway": 2
  },
  "!3dc96682": {
    "num": 1036609154,
    "user": {
      "id": "!3dc96682",
      "longName": "WA9ONY-4\u2013yagi8el",
      "shortName": "ONY4",
      "macaddr": "fa:d1:3d:c9:66:82",
      "hwModel": "T_ECHO",
      "publicKey": "yEBY0uAXm+ez/Zrbv+ePw3WxbFj3H5yinEPGvlaUmhQ="
    },
    "position": {
      "latitudeI": 456687306,
      "longitudeI": -1223862883,
      "altitude": 359,
      "time": 1735486378,
      "locationSource": "LOC_INTERNAL",
      "latitude": 45.6687306,
      "longitude": -122.3862883
    },
    "snr": 6.25,
    "lastHeard": 1735486301,
    "hopsAway": 0,
    "isFavorite": true
  },
  "!bbd0236e": {
    "num": 3150979950,
    "user": {
      "id": "!bbd0236e",
      "longName": "YCM8",
      "shortName": "YCM8",
      "macaddr": "d9:dd:bb:d0:23:6e",
      "hwModel": "RAK4631",
      "role": "ROUTER",
      "publicKey": "jM1Qm4OVlIzkg3V6kNFKIvhZTSBuuG74xj/poJ5wfxM="
    },
    "snr": 7.0,
    "lastHeard": 1735250234,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.36,
      "channelUtilization": 18.191668,
      "airUtilTx": 4.6167502,
      "uptimeSeconds": 2911396
    },
    "hopsAway": 4
  },
  "!4359a410": {
    "num": 1129948176,
    "user": {
      "id": "!4359a410",
      "longName": "Meshtastic a410",
      "shortName": "a410",
      "macaddr": "48:ca:43:59:a4:10",
      "hwModel": "HELTEC_V3",
      "role": "CLIENT_MUTE",
      "publicKey": "kY0EqOsprKqrhrBsMczX9JhE7IOCgxAYxbi/dYtpWgo="
    },
    "snr": 6.25,
    "lastHeard": 1735486930,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.214,
      "channelUtilization": 12.578334,
      "airUtilTx": 0.2802778,
      "uptimeSeconds": 900803
    },
    "hopsAway": 5
  },
  "!433beb8c": {
    "num": 1128000396,
    "user": {
      "id": "!433beb8c",
      "longName": "digitalsoul",
      "shortName": "Ds",
      "macaddr": "48:ca:43:3b:eb:8c",
      "hwModel": "HELTEC_V3",
      "publicKey": "hL0reZRjAMB6vOKtkjxQe1eVV2qNuayELRRHx/kUjx8="
    },
    "position": {
      "latitudeI": 455213056,
      "longitudeI": -1229062144,
      "altitude": 64,
      "time": 1735486769,
      "locationSource": "LOC_EXTERNAL",
      "latitude": 45.5213056,
      "longitude": -122.9062144
    },
    "snr": 6.0,
    "lastHeard": 1735486825,
    "deviceMetrics": {
      "batteryLevel": 88,
      "voltage": 4.042,
      "channelUtilization": 5.9700003,
      "airUtilTx": 0.7641111,
      "uptimeSeconds": 936367
    },
    "hopsAway": 7
  },
  "!7837522e": {
    "num": 2016891438,
    "user": {
      "id": "!7837522e",
      "longName": "WST1 \ud83d\ude80",
      "shortName": "WST1",
      "macaddr": "e5:f9:78:37:52:2e",
      "hwModel": "RAK4631",
      "publicKey": "n0o7gHR+gsm63W8tYe3K8sdB1M0ce8LbXaGXnqw/tS8="
    },
    "snr": 6.0,
    "lastHeard": 1735233741,
    "hopsAway": 5
  },
  "!7d67a8b7": {
    "num": 2103945399,
    "user": {
      "id": "!7d67a8b7",
      "longName": "WA9ONY-1-window ",
      "shortName": "ONY1",
      "macaddr": "e1:0b:7d:67:a8:b7",
      "hwModel": "T_ECHO",
      "publicKey": "aom7Ro1eI3sC5GKWPKI88Uj5mRO6OpzIOXoB568KbH0="
    },
    "snr": 6.25,
    "lastHeard": 1735486080,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.931,
      "channelUtilization": 23.935001,
      "airUtilTx": 4.5458055,
      "uptimeSeconds": 85379
    },
    "hopsAway": 0
  },
  "!6741fbf3": {
    "num": 1732377587,
    "user": {
      "id": "!6741fbf3",
      "longName": "WA9ONY-7",
      "shortName": "ONY7",
      "macaddr": "c8:11:67:41:fb:f3",
      "hwModel": "T_ECHO",
      "publicKey": "VyF/I4XpHPYGx6sCrYqvZ0A5IeZYVUNhXfy2kXzqm3c="
    },
    "position": {
      "latitudeI": 456685420,
      "longitudeI": -1223861942,
      "altitude": 342,
      "time": 1735487996,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.668542,
      "longitude": -122.3861942
    },
    "snr": 6.5,
    "lastHeard": 1735488018,
    "hopsAway": 0,
    "isFavorite": true
  },
  "!433dea4c": {
    "num": 1128131148,
    "user": {
      "id": "!433dea4c",
      "longName": "Meshtastic ea4c",
      "shortName": "\ud83d\udc19",
      "macaddr": "48:ca:43:3d:ea:4c",
      "hwModel": "HELTEC_WSL_V3",
      "publicKey": "Rz/zsCeo1w/8zNwjvDNk/rT4Ot7C9ofKRhwJ64Qhiiw="
    },
    "position": {
      "latitudeI": 453771264,
      "longitudeI": -1226571776,
      "altitude": 213,
      "time": 1735485363,
      "latitude": 45.3771264,
      "longitude": -122.6571776
    },
    "snr": 6.0,
    "lastHeard": 1735485392,
    "deviceMetrics": {
      "batteryLevel": 15,
      "voltage": 3.361,
      "channelUtilization": 13.806666,
      "airUtilTx": 0.044694442,
      "uptimeSeconds": 46
    },
    "hopsAway": 2
  },
  "!433ac354": {
    "num": 1127924564,
    "user": {
      "id": "!433ac354",
      "longName": "Meshtastic c354",
      "shortName": "c354",
      "macaddr": "48:ca:43:3a:c3:54",
      "hwModel": "HELTEC_V3",
      "publicKey": "xeMifmgR6D775EZ2Uq1dP7GUVGlcf0AEbvrKLxOpZn8="
    },
    "snr": 5.75,
    "lastHeard": 1735239210,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.234,
      "channelUtilization": 16.961666,
      "airUtilTx": 5.504306,
      "uptimeSeconds": 524752
    },
    "hopsAway": 2
  },
  "!c4f7c8c8": {
    "num": 3304573128,
    "user": {
      "id": "!c4f7c8c8",
      "longName": "Warren",
      "shortName": "c8c8",
      "macaddr": "24:0a:c4:f7:c8:c8",
      "hwModel": "TBEAM",
      "publicKey": "cif8v0DmLwVBeqbzNm5/eb6qa18ffBVt90M/QRP4rkc="
    },
    "position": {
      "latitudeI": 455229063,
      "longitudeI": -1228979141,
      "altitude": 45,
      "time": 1735242461,
      "latitude": 45.5229063,
      "longitude": -122.8979141
    },
    "snr": 5.5,
    "lastHeard": 1735242481,
    "hopsAway": 4
  },
  "!5b4a1227": {
    "num": 1531580967,
    "user": {
      "id": "!5b4a1227",
      "longName": "\ud83e\uddab_1227",
      "shortName": "\ud83e\uddab",
      "macaddr": "ce:96:5b:4a:12:27",
      "hwModel": "RAK4631",
      "publicKey": "u7cD5VtBFLeMrtvfpMd7WXuF9wVu/U3OdFioAp1XBQQ="
    },
    "position": {
      "latitudeI": 454688768,
      "longitudeI": -1226178560,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.4688768,
      "longitude": -122.617856
    },
    "snr": 6.25,
    "lastHeard": 1735486290,
    "deviceMetrics": {
      "batteryLevel": 99,
      "voltage": 4.187,
      "channelUtilization": 24.806667,
      "airUtilTx": 5.6338887,
      "uptimeSeconds": 84763
    },
    "hopsAway": 3
  },
  "!4338af48": {
    "num": 1127788360,
    "user": {
      "id": "!4338af48",
      "longName": "ChannelLink LF",
      "shortName": "CLLF",
      "macaddr": "48:ca:43:38:af:48",
      "hwModel": "HELTEC_V3",
      "publicKey": "4GzfyB0IyZAQtOjvGRILhXfSuiKdKanyPQYcAmJfqU8="
    },
    "snr": 7.0,
    "lastHeard": 1735488432,
    "deviceMetrics": {
      "batteryLevel": 90,
      "voltage": 4.057,
      "channelUtilization": 17.893333,
      "airUtilTx": 4.5564165,
      "uptimeSeconds": 235336
    },
    "hopsAway": 2
  },
  "!eb8b5807": {
    "num": 3951777799,
    "user": {
      "id": "!eb8b5807",
      "longName": "Meshtastic 5807",
      "shortName": "5807",
      "macaddr": "d6:db:eb:8b:58:07",
      "hwModel": "T_ECHO",
      "role": "CLIENT_MUTE",
      "publicKey": "j9MYPjkrmdT7IjoJqHuVV5mqikcweRqiy+VoRc9ndXM="
    },
    "position": {
      "latitudeI": 454295552,
      "longitudeI": -1224998912,
      "altitude": -1,
      "time": 1735278301,
      "locationSource": "LOC_INTERNAL",
      "latitude": 45.4295552,
      "longitude": -122.4998912
    },
    "snr": 6.5,
    "lastHeard": 1735278458,
    "deviceMetrics": {
      "batteryLevel": 81,
      "voltage": 3.996,
      "channelUtilization": 11.5616665,
      "airUtilTx": 0.09302778,
      "uptimeSeconds": 23003
    },
    "hopsAway": 3
  },
  "!874afcc4": {
    "num": 2269838532,
    "user": {
      "id": "!874afcc4",
      "longName": "Falcon \u26a0\ufe0f",
      "shortName": "FMNA",
      "macaddr": "eb:a3:87:4a:fc:c4",
      "hwModel": "RAK4631",
      "role": "CLIENT_MUTE",
      "publicKey": "NKOdljSh2qHT43WD5wSU2depnE4KoZgABfPB5NdkchA="
    },
    "snr": 6.25,
    "lastHeard": 1735232566,
    "deviceMetrics": {
      "batteryLevel": 71,
      "voltage": 3.9,
      "channelUtilization": 9.771667,
      "airUtilTx": 0.06791666,
      "uptimeSeconds": 409229
    },
    "hopsAway": 5
  },
  "!499336fd": {
    "num": 1234384637,
    "user": {
      "id": "!499336fd",
      "longName": "WA9ONY-2-shack",
      "shortName": "ONY2",
      "macaddr": "e1:29:49:93:36:fd",
      "hwModel": "T_ECHO",
      "publicKey": "1oozH0aCbdQFPlSZG7MhRmFmIseOtAohViofJuTmbRk="
    },
    "snr": 5.75,
    "lastHeard": 1735278311,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.654,
      "channelUtilization": 22.586666,
      "airUtilTx": 3.750639,
      "uptimeSeconds": 82263
    },
    "hopsAway": 0
  },
  "!a125fef4": {
    "num": 2703621876,
    "user": {
      "id": "!a125fef4",
      "longName": "WA9ONY-6-attic",
      "shortName": "ONY6",
      "macaddr": "f0:99:a1:25:fe:f4",
      "hwModel": "T_ECHO",
      "publicKey": "VyF/I4XpHPYGx6sCrYqvZ0A5IeZYVUNhXfy2kXzqm3c="
    },
    "position": {
      "latitudeI": 456685352,
      "longitudeI": -1223861716,
      "altitude": 339,
      "time": 1735487904,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.6685352,
      "longitude": -122.3861716
    },
    "snr": 6.5,
    "lastHeard": 1735487900,
    "deviceMetrics": {
      "batteryLevel": 92,
      "voltage": 4.088,
      "channelUtilization": 22.331667,
      "airUtilTx": 3.462222,
      "uptimeSeconds": 487398
    },
    "hopsAway": 0
  },
  "!af0e93f3": {
    "num": 2936968179,
    "user": {
      "id": "!af0e93f3",
      "longName": "Meshtastic 93f3",
      "shortName": "93f3",
      "macaddr": "d8:e7:af:0e:93:f3",
      "hwModel": "RAK4631",
      "publicKey": "KWD0wc0JU86k1QOLJ6JPRiaz8pwT7++Qs4eukA4MDFA="
    },
    "snr": 5.75,
    "lastHeard": 1735486100,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.28,
      "channelUtilization": 17.67,
      "airUtilTx": 4.789361,
      "uptimeSeconds": 36654
    },
    "hopsAway": 5
  },
  "!43594854": {
    "num": 1129924692,
    "user": {
      "id": "!43594854",
      "longName": "Meshtastic 4854",
      "shortName": "4854",
      "macaddr": "48:ca:43:59:48:54",
      "hwModel": "HELTEC_V3",
      "publicKey": "1GuZi5jQ8N8KSAzEHAbv+3uMzZx4Am0x8IlF1ipz9Qc="
    },
    "position": {
      "latitudeI": 455868416,
      "longitudeI": -1226571776,
      "altitude": 25,
      "time": 1735252727,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.5868416,
      "longitude": -122.6571776
    },
    "snr": 5.75,
    "lastHeard": 1735252804,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.244,
      "channelUtilization": 19.026667,
      "airUtilTx": 3.8372502,
      "uptimeSeconds": 6216839
    },
    "hopsAway": 3
  },
  "!43b6b778": {
    "num": 1136047992,
    "user": {
      "id": "!43b6b778",
      "longName": "Cortex",
      "shortName": "Crtx",
      "macaddr": "48:ca:43:b6:b7:78",
      "hwModel": "HELTEC_V3",
      "publicKey": "XQ4El8aNDdePMW71LdIeUMx4T1d3o78HYbXRDiD9WjI="
    },
    "position": {
      "latitudeI": 456392704,
      "longitudeI": -1225523200,
      "time": 1735252295,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.6392704,
      "longitude": -122.55232
    },
    "snr": 6.5,
    "lastHeard": 1735252317,
    "deviceMetrics": {
      "batteryLevel": 96,
      "voltage": 4.137,
      "channelUtilization": 9.141666,
      "airUtilTx": 2.7151113,
      "uptimeSeconds": 1019272
    },
    "hopsAway": 3
  },
  "!4581dfae": {
    "num": 1166139310,
    "user": {
      "id": "!4581dfae",
      "longName": "pdxlocs LongFast ",
      "shortName": "pdxL",
      "macaddr": "cf:6f:45:81:df:ae",
      "hwModel": "RAK4631",
      "publicKey": "I4jHM+XVUJt8K0R6YH3fUrzNhvYN+13V4tzZCzJfPUc="
    },
    "position": {
      "latitudeI": 454393856,
      "longitudeI": -1227194368,
      "altitude": 187,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.4393856,
      "longitude": -122.7194368
    },
    "snr": 6.5,
    "lastHeard": 1735489089,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.123,
      "channelUtilization": 3.1883333,
      "airUtilTx": 5.1559725,
      "uptimeSeconds": 80111
    },
    "hopsAway": 3
  },
  "!e2e3772c": {
    "num": 3806557996,
    "user": {
      "id": "!e2e3772c",
      "longName": "Robotic Assistant Labor Facilitator",
      "shortName": "RALF",
      "macaddr": "48:27:e2:e3:77:2c",
      "hwModel": "HELTEC_V3",
      "publicKey": "/0pomUFsHNHewqLp6Bx0rM5+0ZeY6yRXFXdSF6qHnzw="
    },
    "position": {
      "latitudeI": 454721536,
      "longitudeI": -1226014720,
      "altitude": 69,
      "time": 1735487947,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.4721536,
      "longitude": -122.601472
    },
    "snr": 5.75,
    "lastHeard": 1735488015,
    "deviceMetrics": {
      "batteryLevel": 97,
      "voltage": 4.155,
      "channelUtilization": 23.119999,
      "airUtilTx": 3.5236669,
      "uptimeSeconds": 5031598
    },
    "hopsAway": 2
  },
  "!1c497d70": {
    "num": 474578288,
    "user": {
      "id": "!1c497d70",
      "longName": "WSR3",
      "shortName": "WSR3",
      "macaddr": "10:06:1c:49:7d:70",
      "hwModel": "TBEAM",
      "publicKey": "pw8zaEW/nYuPn17vCG6Ie2riNBK7/UNey3Lg2EfW2Ec="
    },
    "position": {
      "latitudeI": 452198400,
      "longitudeI": -1226047488,
      "altitude": 38,
      "time": 1735228770,
      "latitude": 45.21984,
      "longitude": -122.6047488
    },
    "snr": 7.25,
    "lastHeard": 1735228792,
    "hopsAway": 3
  },
  "!7fcfda8d": {
    "num": 2144328333,
    "user": {
      "id": "!7fcfda8d",
      "longName": "Falcon",
      "shortName": "FMN1",
      "macaddr": "d3:cd:7f:cf:da:8d",
      "hwModel": "RAK4631",
      "publicKey": "ytmkf6S2MshX1gpVuxN3YmRN7VIuyMn8nvXPIeg37lk="
    },
    "snr": 5.75,
    "lastHeard": 1735233132,
    "deviceMetrics": {
      "batteryLevel": 94,
      "voltage": 4.112,
      "channelUtilization": 17.791666,
      "airUtilTx": 4.846139,
      "uptimeSeconds": 219126
    },
    "hopsAway": 5
  },
  "!b41de0e1": {
    "num": 3021856993,
    "user": {
      "id": "!b41de0e1",
      "longName": "Meshtastic e0e1",
      "shortName": "e0e1",
      "macaddr": "c1:e7:b4:1d:e0:e1",
      "hwModel": "TRACKER_T1000_E",
      "role": "CLIENT_MUTE",
      "publicKey": "8BwA+yZTG/Y2H4S7EW99ysOwmlaC3kL/03ZZKDC8jis="
    },
    "position": {
      "latitudeI": 454721536,
      "longitudeI": -1226145792,
      "altitude": 37,
      "time": 1735251918,
      "locationSource": "LOC_INTERNAL",
      "latitude": 45.4721536,
      "longitude": -122.6145792
    },
    "snr": 6.5,
    "lastHeard": 1735251934,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.162,
      "channelUtilization": 19.491667,
      "airUtilTx": 0.31741667,
      "uptimeSeconds": 15967
    },
    "hopsAway": 3
  },
  "!bd50377c": {
    "num": 3176150908,
    "user": {
      "id": "!bd50377c",
      "longName": "SOLO",
      "shortName": "SOLO",
      "macaddr": "f0:f5:bd:50:37:7c",
      "hwModel": "HELTEC_V3",
      "role": "CLIENT_MUTE",
      "publicKey": "h64QJ62BohcqFeN6Wg1ybRwN6g8u3NocOD6HcHKWCmU="
    },
    "snr": 6.25,
    "lastHeard": 1735246881,
    "deviceMetrics": {
      "batteryLevel": 0,
      "voltage": 3.095,
      "channelUtilization": 2.4616666,
      "airUtilTx": 0.012555555,
      "uptimeSeconds": 1963978
    },
    "hopsAway": 2
  },
  "!f553f106": {
    "num": 4115919110,
    "user": {
      "id": "!f553f106",
      "longName": "Shrimp Mobile",
      "shortName": "SHMB",
      "macaddr": "f2:0f:f5:53:f1:06",
      "hwModel": "RAK4631",
      "publicKey": "TebEMCgRs5pV1Nq9xCG+JrIyQJzC24gOHqhI9zzfK30="
    },
    "position": {
      "latitudeI": 454688768,
      "longitudeI": -1226440704,
      "altitude": 44,
      "time": 1735487921,
      "locationSource": "LOC_INTERNAL",
      "latitude": 45.4688768,
      "longitude": -122.6440704
    },
    "snr": 6.25,
    "lastHeard": 1735488243,
    "deviceMetrics": {
      "batteryLevel": 36,
      "voltage": 3.594,
      "channelUtilization": 21.566668,
      "airUtilTx": 4.031722,
      "uptimeSeconds": 113469
    },
    "hopsAway": 3
  },
  "!57016335": {
    "num": 1459708725,
    "user": {
      "id": "!57016335",
      "longName": "Mount Scott",
      "shortName": "HVMS",
      "macaddr": "ca:58:57:01:63:35",
      "hwModel": "RAK4631",
      "publicKey": "XDEFD7lyIn3uMcmkL7syUyonDzT30cljx2waSOuNj1o="
    },
    "snr": 5.75,
    "lastHeard": 1735251822,
    "deviceMetrics": {
      "batteryLevel": 70,
      "voltage": 3.897,
      "channelUtilization": 19.336666,
      "airUtilTx": 4.9954166,
      "uptimeSeconds": 86826
    },
    "hopsAway": 2
  },
  "!33790214": {
    "num": 863568404,
    "user": {
      "id": "!33790214",
      "longName": "The Nebuchadnezzar",
      "shortName": "Neo",
      "macaddr": "64:e8:33:79:02:14",
      "hwModel": "HELTEC_VISION_MASTER_T190",
      "publicKey": "7e7B15QhEkTTmyXwIFikgBjnSXgi4hZ9w3xIfXxqvSo="
    },
    "position": {
      "latitudeI": 453771264,
      "longitudeI": -1226571776,
      "altitude": 217,
      "time": 1735249461,
      "locationSource": "LOC_EXTERNAL",
      "latitude": 45.3771264,
      "longitude": -122.6571776
    },
    "snr": 6.75,
    "lastHeard": 1735253042,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.206,
      "channelUtilization": 17.615,
      "airUtilTx": 4.19025,
      "uptimeSeconds": 5693
    },
    "hopsAway": 7
  },
  "!33679cd4": {
    "num": 862428372,
    "user": {
      "id": "!33679cd4",
      "longName": "\ud83e\udebc",
      "shortName": "\ud83e\udebc",
      "macaddr": "64:e8:33:67:9c:d4",
      "hwModel": "HELTEC_WIRELESS_PAPER",
      "role": "ROUTER",
      "publicKey": "ydVel8jgtgIQVgnA4w7g0vNVvnyXEHAP5crXMYb5x1Y="
    },
    "position": {
      "latitudeI": 436994048,
      "longitudeI": -1226047488,
      "altitude": 1488,
      "locationSource": "LOC_MANUAL",
      "latitude": 43.6994048,
      "longitude": -122.6047488
    },
    "snr": 6.0,
    "lastHeard": 1735488224,
    "hopsAway": 2
  },
  "!a1a8dee1": {
    "num": 2712198881,
    "user": {
      "id": "!a1a8dee1",
      "longName": "NET dee1",
      "shortName": "dee1",
      "macaddr": "f8:c3:a1:a8:de:e1",
      "hwModel": "RAK4631",
      "publicKey": "INAWiGo67JcGG5dWwZdeHgmhxPFT0Jmf9DTH7MIG5B4="
    },
    "position": {
      "latitudeI": 455344128,
      "longitudeI": -1224998912,
      "altitude": 30,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.5344128,
      "longitude": -122.4998912
    },
    "snr": 6.5,
    "lastHeard": 1735488053,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.129,
      "channelUtilization": 5.8316665,
      "airUtilTx": 2.2249722,
      "uptimeSeconds": 398802
    },
    "hopsAway": 3
  },
  "!fbb6131c": {
    "num": 4223013660,
    "user": {
      "id": "!fbb6131c",
      "longName": "T-ECHO_0",
      "shortName": "TEC0",
      "macaddr": "ed:24:fb:b6:13:1c",
      "hwModel": "T_ECHO",
      "publicKey": "iWVKVwExfi3USkBfFk4fcLXDp11dFrPWfhy/sC04cSU="
    },
    "snr": 6.0,
    "lastHeard": 1735239856,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.796,
      "channelUtilization": 6.215,
      "airUtilTx": 1.4781667,
      "uptimeSeconds": 84285
    },
    "hopsAway": 3
  },
  "!b7e6f9e0": {
    "num": 3085367776,
    "user": {
      "id": "!b7e6f9e0",
      "longName": "T1000-\ud83c\udf83",
      "shortName": "\ud83c\udf83",
      "macaddr": "f5:0f:b7:e6:f9:e0",
      "hwModel": "TRACKER_T1000_E",
      "role": "CLIENT_MUTE",
      "publicKey": "n71jei/uNpIqJdRZ4ZF5fVdjUOJ8adaFjQKrqOiZfhY="
    },
    "position": {
      "latitudeI": 456392704,
      "longitudeI": -1226571776,
      "altitude": 54,
      "time": 1735487410,
      "locationSource": "LOC_INTERNAL",
      "latitude": 45.6392704,
      "longitude": -122.6571776
    },
    "snr": 6.0,
    "lastHeard": 1735487464,
    "deviceMetrics": {
      "batteryLevel": 74,
      "voltage": 3.932,
      "channelUtilization": 18.558334,
      "airUtilTx": 0.05908333,
      "uptimeSeconds": 69615
    },
    "hopsAway": 3
  },
  "!8483da2c": {
    "num": 2223233580,
    "user": {
      "id": "!8483da2c",
      "longName": "Killingsworth #17",
      "shortName": "\ud83d\ude8e",
      "macaddr": "f2:f6:84:83:da:2c",
      "hwModel": "RAK4631",
      "publicKey": "t83aPnfhY2LwwBCAnH8G+fDBwAc7G03sIPYUfuTq030="
    },
    "position": {
      "latitudeI": 455632794,
      "longitudeI": -1226380357,
      "altitude": 60,
      "time": 1735250698,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.5632794,
      "longitude": -122.6380357
    },
    "snr": 6.75,
    "lastHeard": 1735250726,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.098,
      "channelUtilization": 12.771666,
      "airUtilTx": 4.201722,
      "uptimeSeconds": 1608427
    },
    "hopsAway": 2
  },
  "!da5ec1b8": {
    "num": 3663643064,
    "user": {
      "id": "!da5ec1b8",
      "longName": "moo attic heltec",
      "shortName": "moo0",
      "macaddr": "34:b7:da:5e:c1:b8",
      "hwModel": "HELTEC_WIRELESS_TRACKER",
      "publicKey": "7ufyFvXqplVFVAfLEeD/2eXjkCK+X1AmBVvwSLrbbyc="
    },
    "position": {
      "latitudeI": 455836225,
      "longitudeI": -1226938460,
      "time": 1735247495,
      "latitude": 45.5836225,
      "longitude": -122.693846
    },
    "snr": 6.25,
    "lastHeard": 1735247522,
    "hopsAway": 3
  },
  "!1c497d50": {
    "num": 474578256,
    "user": {
      "id": "!1c497d50",
      "longName": "JASpier",
      "shortName": "Jill",
      "macaddr": "10:06:1c:49:7d:50",
      "hwModel": "TBEAM",
      "publicKey": "BhuGfcCasdZT6TGLbygecBljtx/6uDF8VXs+C32RWT8="
    },
    "snr": 6.75,
    "lastHeard": 1735488128,
    "hopsAway": 6
  },
  "!f18dd716": {
    "num": 4052604694,
    "user": {
      "id": "!f18dd716",
      "longName": "TMesh",
      "shortName": "Tmsh",
      "macaddr": "e0:f5:f1:8d:d7:16",
      "hwModel": "T_ECHO",
      "publicKey": "8fjCa/4ckEaoME6fzWo2MMsMJabR0tvStHbK8a6QoQM="
    },
    "snr": 6.0,
    "lastHeard": 1735486786,
    "hopsAway": 2
  },
  "!4355f714": {
    "num": 1129707284,
    "user": {
      "id": "!4355f714",
      "longName": "ravenium",
      "shortName": "\ud83e\udeb6",
      "macaddr": "48:ca:43:55:f7:14",
      "hwModel": "HELTEC_V3",
      "publicKey": "BhuSDSIF54Pl4V9/AUTumG7PA9v1vFEux5L1WC6VWz8="
    },
    "position": {
      "latitudeI": 455344128,
      "longitudeI": -1229193216,
      "altitude": 54,
      "time": 1735486043,
      "latitude": 45.5344128,
      "longitude": -122.9193216
    },
    "snr": 6.0,
    "lastHeard": 1735489177,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.224,
      "channelUtilization": 0.0,
      "airUtilTx": 1.0636667,
      "uptimeSeconds": 245112
    },
    "hopsAway": 6
  },
  "!43b7b918": {
    "num": 1136113944,
    "user": {
      "id": "!43b7b918",
      "longName": "Montavilla UNIX",
      "shortName": "UN1X",
      "macaddr": "48:ca:43:b7:b9:18",
      "hwModel": "HELTEC_V3",
      "publicKey": "OexUb1erBt6KbEVtrsmpNvAJsZN09GPIXH45BufaHFs="
    },
    "position": {
      "latitudeI": 455106560,
      "longitudeI": -1225809920,
      "altitude": 81,
      "time": 1735486892,
      "locationSource": "LOC_MANUAL",
      "latitude": 45.510656,
      "longitude": -122.580992
    },
    "snr": 6.25,
    "lastHeard": 1735486901,
    "deviceMetrics": {
      "batteryLevel": 90,
      "voltage": 4.056,
      "channelUtilization": 5.4166665,
      "airUtilTx": 1.90925,
      "uptimeSeconds": 241810
    },
    "hopsAway": 1
  },
  "!33602884": {
    "num": 861939844,
    "user": {
      "id": "!33602884",
      "longName": "KK7UIL-1",
      "shortName": "JAS1",
      "macaddr": "64:e8:33:60:28:84",
      "hwModel": "LILYGO_TBEAM_S3_CORE",
      "publicKey": "OntH+ooCkVYHI7voyy3HqD+ztjcQ6wUajjDnoCrIISY="
    },
    "position": {
      "latitudeI": 449576960,
      "longitudeI": -1229717504,
      "altitude": 54,
      "time": 1735222947,
      "locationSource": "LOC_INTERNAL",
      "latitude": 44.957696,
      "longitude": -122.9717504
    },
    "snr": 6.0,
    "lastHeard": 1735251208,
    "deviceMetrics": {
      "batteryLevel": 100,
      "voltage": 4.09,
      "channelUtilization": 12.806667,
      "airUtilTx": 2.5026388,
      "uptimeSeconds": 158578
    },
    "hopsAway": 5
  },
  "!39bbdafb": {
    "num": 968612603,
    "user": {
      "id": "!39bbdafb",
      "longName": "Falcon2",
      "shortName": "FMN2",
      "macaddr": "d4:1e:39:bb:da:fb",
      "hwModel": "RAK4631",
      "role": "CLIENT_MUTE",
      "publicKey": "Ps64XHwYCRigtqeZRLCOekSPGYejniGpJTIt6QpniTw="
    },
    "snr": 6.25,
    "lastHeard": 1735240998,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.1,
      "channelUtilization": 14.35,
      "airUtilTx": 0.052861113,
      "uptimeSeconds": 418766
    },
    "hopsAway": 5
  },
  "!433ae760": {
    "num": 1127933792,
    "user": {
      "id": "!433ae760",
      "longName": "W7MSR2",
      "shortName": "e760",
      "macaddr": "48:ca:43:3a:e7:60",
      "hwModel": "HELTEC_V3",
      "publicKey": "RQIe9r2/ZbQfwQmB9fzCsblD+hLMhf7IRQLsXXvJXQ8="
    },
    "snr": 6.25,
    "lastHeard": 1735227365,
    "hopsAway": 5
  },
  "!9839eafb": {
    "num": 2553932539,
    "user": {
      "id": "!9839eafb",
      "longName": "PVS Roof 2",
      "shortName": "JWR2",
      "macaddr": "f6:1f:98:39:ea:fb",
      "hwModel": "RAK4631",
      "publicKey": "C5xz2SogdtlUGkIMbQynWcejST3E1HvGmp0p3u/inz8="
    },
    "snr": 7.0,
    "lastHeard": 1735252778,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.259,
      "channelUtilization": 22.378332,
      "airUtilTx": 4.3810277,
      "uptimeSeconds": 18064
    },
    "hopsAway": 1
  },
  "!8fcd413a": {
    "num": 2412593466,
    "user": {
      "id": "!8fcd413a",
      "longName": "Meshtastic 413a",
      "shortName": "413a",
      "macaddr": "ff:22:8f:cd:41:3a",
      "hwModel": "RAK4631",
      "publicKey": "mp37eKY3xlaaDq5HsvKahPLDh0WjhgEyhDZ74HCk5Xo="
    },
    "snr": 6.5,
    "lastHeard": 1735246611,
    "hopsAway": 3
  },
  "!4fd0f0ef": {
    "num": 1339093231,
    "user": {
      "id": "!4fd0f0ef",
      "longName": "Meshtastic f0ef",
      "shortName": "f0ef",
      "macaddr": "c4:e7:4f:d0:f0:ef",
      "hwModel": "RAK4631",
      "publicKey": "ncgbFlyzkjZ0SftTzbHJPo8cfLWl4TN5PKPaZDRBeC8="
    },
    "snr": 6.25,
    "lastHeard": 1735236867,
    "hopsAway": 1
  },
  "!7d77bf71": {
    "num": 2104999793,
    "user": {
      "id": "!7d77bf71",
      "longName": "Meshtastic bf71",
      "shortName": "bf71",
      "macaddr": "e0:b0:7d:77:bf:71",
      "hwModel": "RAK4631",
      "publicKey": "HbIYrLEb0yRjYM0+YBpSzEFEY6wnOREXP/TKLxtrlkQ="
    },
    "snr": 5.5,
    "lastHeard": 1735246413,
    "deviceMetrics": {
      "batteryLevel": 101,
      "voltage": 4.076,
      "channelUtilization": 23.276667,
      "airUtilTx": 7.332611,
      "uptimeSeconds": 9967
    },
    "hopsAway": 3
  },
  "!433ac794": {
    "num": 1127925652,
    "user": {
      "id": "!433ac794",
      "longName": "KG7QLE3",
      "shortName": "QLE3",
      "macaddr": "48:ca:43:3a:c7:94",
      "hwModel": "HELTEC_V3",
      "publicKey": "3NkUlQk4iqy5wIfM3l+zhgL4apwkpvmdXFBQNqOPLXw="
    },
    "position": {
      "latitudeI": 452198400,
      "longitudeI": -1231814656,
      "altitude": 51,
      "time": 1735488365,
      "latitude": 45.21984,
      "longitude": -123.1814656
    },
    "snr": 6.25,
    "lastHeard": 1735488395
  },
  "!e0ce1f54": {
    "num": 3771604820,
    "user": {
      "id": "!e0ce1f54",
      "longName": "Happy Hill",
      "shortName": "high",
      "macaddr": "08:f9:e0:ce:1f:54",
      "hwModel": "HELTEC_V2_0",
      "publicKey": "BddKHuvglO7FrXj4F79PxDgkDrI5s2qo5UUWYe6ebDg="
    },
    "snr": 6.25,
    "lastHeard": 1735245322,
    "hopsAway": 3
  },
  "!da65c240": {
    "num": 3664101952,
    "user": {
      "id": "!da65c240",
      "longName": "YCM7",
      "shortName": "YCM7",
      "macaddr": "34:b7:da:65:c2:40",
      "hwModel": "HELTEC_V3",
      "publicKey": "ekekd2kgxsrhkT0u9qlh5Uipp/9EgHHP+aGQ3Xzo4DY="
    },
    "snr": 6.25,
    "lastHeard": 1735245912,
    "hopsAway": 5
  },
  "!0ad99a53": {
    "num": 182032979,
    "user": {
      "id": "!0ad99a53",
      "longName": "LocsTracker (via MF)",
      "shortName": "\ud83d\udd05",
      "macaddr": "d8:b4:0a:d9:9a:53",
      "hwModel": "TRACKER_T1000_E",
      "role": "CLIENT_MUTE",
      "publicKey": "aYdFOTdPeYj26tMxawPD/Cfqs0g8HjNcKfVevoYz7Qg="
    },
    "position": {
      "latitudeI": 454406933,
      "longitudeI": -1227174333,
      "altitude": 203,
      "time": 1735485454,
      "locationSource": "LOC_INTERNAL",
      "latitude": 45.4406933,
      "longitude": -122.7174333
    },
    "snr": 6.25,
    "lastHeard": 1735485465,
    "hopsAway": 2
  },
  "!4e4177b3": {
    "num": 1312913331,
    "user": {
      "id": "!4e4177b3",
      "longName": "pdxlocs D (via MF)",
      "shortName": "pdxD",
      "macaddr": "2c:cf:67:4f:d8:74",
      "hwModel": "PORTDUINO",
      "publicKey": "oY1Se6ZaVvrFQk/bu4q4BQ1PiRfUXB6G9du/sTcg4H0="
    },
    "snr": 6.25,
    "lastHeard": 1735278352,
    "hopsAway": 3
  },
  "!433b8cd8": {
    "num": 1127976152,
    "user": {
      "id": "!433b8cd8",
      "longName": "McCutie (via MF)",
      "shortName": "MCU",
      "macaddr": "48:ca:43:3b:8c:d8",
      "hwModel": "HELTEC_WIRELESS_PAPER",
      "role": "CLIENT_MUTE",
      "publicKey": "W5ZyRm/qF27rrGbfvyx9meKd3BjVeqWanQK73IjxM2c="
    },
    "position": {
      "latitudeI": 454426624,
      "longitudeI": -1227227136,
      "altitude": 162,
      "time": 1735487754,
      "locationSource": "LOC_EXTERNAL",
      "latitude": 45.4426624,
      "longitude": -122.7227136
    },
    "snr": 6.75,
    "lastHeard": 1735487784,
    "hopsAway": 2
  },
  "!60bffc13": {
    "num": 1623194643,
    "user": {
      "id": "!60bffc13",
      "longName": "pdxlocs MediumFast (via MF)",
      "shortName": "pdxM",
      "macaddr": "e4:bf:60:bf:fc:13",
      "hwModel": "RAK4631",
      "publicKey": "80aXcnYsRI6MmVbap/lf6FRwLwUdlltoIA6TqCJN2EQ="
    },
    "position": {
      "latitudeI": 454404888,
      "longitudeI": -1227173903,
      "altitude": 187,
      "time": 1735433377,
      "locationSource": "LOC_EXTERNAL",
      "latitude": 45.4404888,
      "longitude": -122.7173903
    },
    "snr": 5.75,
    "lastHeard": 1735486231,
    "hopsAway": 2
  },
  "!c4f7cb6c": {
    "num": 3304573804,
    "user": {
      "id": "!c4f7cb6c",
      "longName": "Arnold Creek",
      "shortName": "AC",
      "macaddr": "24:0a:c4:f7:cb:6c",
      "hwModel": "TBEAM",
      "publicKey": "szTUWlx3ST6CjaHTmEbo/O1oAlae9OPXuavIZKJI9U0="
    },
    "snr": 6.25,
    "lastHeard": 1735486979,
    "hopsAway": 3
  },
  "!43596658": {
    "num": 1129932376,
    "user": {
      "id": "!43596658",
      "longName": "828 Base",
      "shortName": "828B",
      "macaddr": "48:ca:43:59:66:58",
      "hwModel": "HELTEC_V3",
      "publicKey": "Vtss4AR/Kz30A2XPrFOr+O3VW44y6eaVoC06+vOyDlg="
    },
    "snr": 6.25,
    "lastHeard": 1735488091,
    "hopsAway": 5
  },
  "!75e99dd8": {
    "num": 1978244568,
    "user": {
      "id": "!75e99dd8",
      "longName": "Meshtastic 9dd8",
      "shortName": "9dd8",
      "hwModel": "UNSET"
    },
    "snr": 6.25,
    "lastHeard": 1735513051,
    "deviceMetrics": {
      "batteryLevel": 78,
      "voltage": 4.003,
      "channelUtilization": 6.623334,
      "airUtilTx": 5.2760277
    }
  }
}

Preferences: {
  "device": {
    "serialEnabled": true,
    "nodeInfoBroadcastSecs": 10800,
    "role": "CLIENT",
    "buttonGpio": 0,
    "buzzerGpio": 0,
    "rebroadcastMode": "ALL",
    "doubleTapAsButtonPress": false,
    "isManaged": false,
    "disableTripleClick": false,
    "tzdef": "",
    "ledHeartbeatDisabled": false
  },
  "position": {
    "positionBroadcastSecs": 300,
    "positionBroadcastSmartEnabled": true,
    "gpsUpdateInterval": 120,
    "positionFlags": 811,
    "broadcastSmartMinimumDistance": 100,
    "broadcastSmartMinimumIntervalSecs": 30,
    "gpsMode": "ENABLED",
    "fixedPosition": false,
    "gpsEnabled": false,
    "gpsAttemptTime": 0,
    "rxGpio": 0,
    "txGpio": 0,
    "gpsEnGpio": 0
  },
  "power": {
    "waitBluetoothSecs": 60,
    "sdsSecs": 4294967295,
    "lsSecs": 300,
    "minWakeSecs": 10,
    "isPowerSaving": false,
    "onBatteryShutdownAfterSecs": 0,
    "adcMultiplierOverride": 0.0,
    "deviceBatteryInaAddress": 0,
    "powermonEnables": "0"
  },
  "network": {
    "ntpServer": "0.pool.ntp.org",
    "wifiEnabled": false,
    "wifiSsid": "",
    "wifiPsk": "",
    "ethEnabled": false,
    "addressMode": "DHCP",
    "rsyslogServer": ""
  },
  "display": {
    "screenOnSecs": 31536000,
    "gpsFormat": "DEC",
    "autoScreenCarouselSecs": 0,
    "compassNorthTop": false,
    "flipScreen": false,
    "units": "METRIC",
    "oled": "OLED_AUTO",
    "displaymode": "DEFAULT",
    "headingBold": false,
    "wakeOnTapOrMotion": false,
    "compassOrientation": "DEGREES_0"
  },
  "lora": {
    "usePreset": true,
    "region": "US",
    "hopLimit": 7,
    "txEnabled": true,
    "txPower": 30,
    "sx126xRxBoostedGain": true,
    "modemPreset": "LONG_FAST",
    "bandwidth": 0,
    "spreadFactor": 0,
    "codingRate": 0,
    "frequencyOffset": 0.0,
    "channelNum": 0,
    "overrideDutyCycle": false,
    "overrideFrequency": 0.0,
    "paFanDisabled": false,
    "ignoreIncoming": [],
    "ignoreMqtt": false,
    "configOkToMqtt": false
  },
  "bluetooth": {
    "enabled": true,
    "mode": "NO_PIN",
    "fixedPin": 123456
  },
  "security": {
    "publicKey": "5j0wZkhSApxrdD3CeRtABVp5hUcMmcoUkrxnGxucv1k=",
    "privateKey": "yNd+9eSFHIhRGDk5bNu2kYZpYnDTxFDKsFc13UDvVXk=",
    "serialEnabled": true,
    "adminKey": [],
    "isManaged": false,
    "debugLogApiEnabled": false,
    "adminChannelEnabled": false
  },
  "version": 0
}

Module preferences: {
  "mqtt": {
    "address": "mqtt.meshtastic.org",
    "username": "meshdev",
    "password": "large4cats",
    "encryptionEnabled": true,
    "root": "msh/US",
    "enabled": false,
    "jsonEnabled": false,
    "tlsEnabled": false,
    "proxyToClientEnabled": false,
    "mapReportingEnabled": false
  },
  "serial": {
    "enabled": false,
    "echo": false,
    "rxd": 0,
    "txd": 0,
    "baud": "BAUD_DEFAULT",
    "timeout": 0,
    "mode": "DEFAULT",
    "overrideConsoleSerialPort": false
  },
  "externalNotification": {
    "enabled": false,
    "outputMs": 0,
    "output": 0,
    "outputVibra": 0,
    "outputBuzzer": 0,
    "active": false,
    "alertMessage": false,
    "alertMessageVibra": false,
    "alertMessageBuzzer": false,
    "alertBell": false,
    "alertBellVibra": false,
    "alertBellBuzzer": false,
    "usePwm": false,
    "nagTimeout": 0,
    "useI2sAsBuzzer": false
  },
  "storeForward": {
    "enabled": false,
    "heartbeat": false,
    "records": 0,
    "historyReturnMax": 0,
    "historyReturnWindow": 0,
    "isServer": false
  },
  "rangeTest": {
    "enabled": false,
    "sender": 0,
    "save": false
  },
  "telemetry": {
    "environmentMeasurementEnabled": true,
    "environmentScreenEnabled": true,
    "environmentDisplayFahrenheit": true,
    "deviceUpdateInterval": 0,
    "environmentUpdateInterval": 0,
    "airQualityEnabled": false,
    "airQualityInterval": 0,
    "powerMeasurementEnabled": false,
    "powerUpdateInterval": 0,
    "powerScreenEnabled": false,
    "healthMeasurementEnabled": false,
    "healthUpdateInterval": 0
  },
  "cannedMessage": {
    "rotary1Enabled": false,
    "inputbrokerPinA": 0,
    "inputbrokerPinB": 0,
    "inputbrokerPinPress": 0,
    "inputbrokerEventCw": "NONE",
    "inputbrokerEventCcw": "NONE",
    "inputbrokerEventPress": "NONE",
    "updown1Enabled": false,
    "enabled": false,
    "allowInputSource": "",
    "sendBell": false
  },
  "audio": {
    "codec2Enabled": false,
    "pttPin": 0,
    "bitrate": "CODEC2_DEFAULT",
    "i2sWs": 0,
    "i2sSd": 0,
    "i2sDin": 0,
    "i2sSck": 0
  },
  "remoteHardware": {
    "enabled": false,
    "allowUndefinedPinAccess": false,
    "availablePins": []
  },
  "neighborInfo": {
    "enabled": false,
    "updateInterval": 0
  },
  "ambientLighting": {
    "current": 10,
    "red": 102,
    "green": 35,
    "blue": 85,
    "ledState": false
  },
  "detectionSensor": {
    "minimumBroadcastSecs": 45,
    "detectionTriggerType": "LOGIC_HIGH",
    "enabled": false,
    "stateBroadcastSecs": 0,
    "sendBell": false,
    "name": "",
    "monitorPin": 0,
    "usePullup": false
  },
  "paxcounter": {
    "enabled": false,
    "paxcounterUpdateInterval": 0,
    "wifiThreshold": 0,
    "bleThreshold": 0
  },
  "version": 0
}

Channels:
  Index 0: PRIMARY psk=default { "psk": "AQ==", "moduleSettings": { "positionPrecision": 32, "isClientMuted": false }, "channelNum": 0, "name": "", "id": 0, "uplinkEnabled": false, "downlinkEnabled": false }

Primary channel URL: https://meshtastic.org/e/#CgcSAQE6AgggEgwIATgBQAdIAVAeaAE

*** A newer version v2.5.9 is available! Consider running "pip install --upgrade meshtastic" ***

david@raspberrypi5:~ $ 



```


