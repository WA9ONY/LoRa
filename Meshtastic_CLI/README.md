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

Introduction to the [LoRa](https://en.wikipedia.org/wiki/LoRa) 
[Meshtastic](https://en.wikipedia.org/wiki/Meshtastic)  
[CLI](https://en.wikipedia.org/wiki/Command-line_interface) Tool

The LoRa Meshtastic CLI tool is a powerful command-line interface designed to configure, monitor, and interact with Meshtastic devices. Meshtastic is an open-source project that leverages LoRa (Long Range) communication technology to create low-power, long-distance mesh networks, which are particularly useful for scenarios where conventional connectivity (Wi-Fi, cellular) is unavailable or unreliable.

The CLI tool allows users to access and control the Meshtastic device's functionalities without relying on graphical interfaces. This flexibility is ideal for developers, tinkerers, and advanced users who need to script, automate, or perform detailed customizations.

Why Use the Meshtastic CLI Tool?
The Meshtastic CLI tool is essential for:

Configuration: Customize device settings such as channel parameters, power levels, and region-specific options.
Network Management: Monitor network traffic, view connected nodes, and troubleshoot issues.
Scripting and Automation: Automate tasks like firmware updates, mass configuration, or logging.
Debugging: Access detailed logs and device information for diagnosing network problems.
Advanced Features: Explore and enable experimental or less frequently used features.


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


