<div id="top"></div>

<p align="center">
<a href="https://github.com/drew-herron/nats.lv/graphs/contributors">
    <img src="https://img.shields.io/github/contributors/drew-herron/nats.lv.svg?style=flat-square" alt="GitHub Contributors" />
</a>
<a href="https://github.com/drew-herron/nats.lv/stargazers">
    <img src="https://img.shields.io/github/stars/drew-herron/nats.lv.svg?style=flat-square" alt="Stars" />
</a>
<a href="https://github.com/drew-herron/nats.lv/network/members">
    <img src="https://img.shields.io/github/forks/drew-herron/nats.lv.svg?style=flat-square" alt="Forks" />
</a>
<a href="https://github.com/drew-herron/nats.lv/issues">
    <img src="https://img.shields.io/github/issues-raw/drew-herron/nats.lv.svg?style=flat-square" alt="Open Issues" />
</a>
<a href="https://ni.com/labview">
    <img src="https://img.shields.io/badge/language-gray?&style=flat-square" alt="language" /><img src="https://img.shields.io/badge/LabVIEW%202013-FFDB00?style=flat-square" alt="language" />
</a>
<a href="https://github.com/drew-herron/nats.lv/blob/main/LICENSE">
    <img src="https://img.shields.io/github/license/drew-herron/nats.lv?style=flat-square" alt="License" />
</a>
</p>


# LabVIEW NATS Client

<p align="center">
  <img src="https://github.com/drew-herron/nats.lv/raw/gh-pages/images/nats_core_palette.png" alt="NATS Core palette" style="max-width: 100%;><br clear="left"/>
</p>

Neural Autonomic Transport System ([NATS](https://nats.io)) is a lightweight publish/subscribe messaging protocol built on top of TCP/IP that provides at-most-once QoS messaging.

The entire toolkit is written in native LabVIEW and requires no external dependencies to run the code (other than a freely available functioning NATS server).

For an in-depth look at the NATS client protocol, visit the [official documentation](https://docs.nats.io/reference/reference-protocols/nats-protocol). As of May 2022 this documentation still does not cover `HPUB` or `HMSG` and neglects to mention the necessary `<CR><LF>` at the end of a `PUB` or `HPUB` payload. The [Go source code](https://github.com/nats-io/nats.go) was used as a reference to overcome the documentation deficiencies.

To learn more about NATS and to download the free, open-source server application visit [https://nats.io](https://nats.io)

# Installation

You can install NATS Core with VI Package Manager. 

### Requirements
- [LabVIEW](https://www.ni.com/labview) 2013 or later

# Features

  - Written entirely in LabVIEW with no additional package dependencies

  - Supports publishing client commands: `CONNECT`, `PUB`, `HPUB`, `SUB`, `UNSUB`, `PING`, `PONG`

  - Supports reading server messages: `INFO`, `MSG`, `HMSG`, `PING`, `PONG`, `+OK`, `-ERR`

  - Server `INFO` and client `CONNECT` commands kept in JSON format to aid in futureproofing

  - Automatic `PONG` response to server `PING` requests for keep-alive functionality

  - Server/client configuration checks to verify if `HPUB` can be used

  - Supports usage of subscriber queue groups

  - TCP connection refnum exposed to allow use of [LabVIEW 2020 native TLS](https://labviewwiki.org/wiki/VIWeek_2020/Using_the_new_TLS/SSL_functions_in_LabVIEW_2020)

# Getting Started

## Running a NATS Server
Running a NATS server is quick and easy because there is no software installation. You can simply download a [precompiled binary](https://github.com/nats-io/nats-server/releases/latest) from the [official NATS site](https://nats.io/download/) and run it from any location.

***Note:*** The precompiled binary for linux-386 runs on a cRIO 904x without needing to download any other dependencies. Last tested with nats-server v2.8.4 (May 2022).

## Location on Palette

The NATS Core palette is added to the ***Functions >> Data Communication*** palette.

<p align="center">
  <img src="https://github.com/drew-herron/nats.lv/raw/gh-pages/images/data_communication_palette.png" alt="Data Communication palette" style="max-width: 100%;><br clear="left"/>
</p>

## Examples
There are currently two examples included with the NATS Core package: a simple NATS writer and a simple NATS reader. These examples can be accessed through the NI Example Finder ( ***Help >> Find Examples...*** )

<p align="center">
  <img src="https://github.com/drew-herron/nats.lv/raw/gh-pages/images/examples_location.png" alt="Example Finder location" style="max-width: 100%;><br clear="left"/>
</p>
<br>

### Simple Reader Example

<p align="center">
  <img src="https://github.com/drew-herron/nats.lv/raw/gh-pages/images/simple_reader_example.png" alt="reader example" style="max-width: 100%;><br clear="left"/>
</p>
<br>

### Simple Publisher Example

<p align="center">
  <img src="https://github.com/drew-herron/nats.lv/raw/gh-pages/images/simple_writer_example.png" alt="writer example" style="max-width: 100%;><br clear="left"/>
</p>


# JetStream

This is not a JetStream enabled client.

# Contributing

Contributions are what make the open source community such an amazing place to be, learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (git checkout -b feature/AmazingFeature)
3. Commit your Changes (git commit -m 'Add some AmazingFeature')
4. Push to the Branch (git push origin feature/AmazingFeature)
5. Open a Pull Request

Keep in mind that LabVIEW VIs are binary files, which are difficult to merge.

- Only change a single VI or library.
- Avoid conflicts with other pull requests (don't work on the same libraries or VIs).
- Send VI Snippets (via issues) instead of pull requests when possible.

*This section shamelessly stolen from the [LabVIEW Composition](https://github.com/LogMANOriginal/LabVIEW-Composition) project. I couldn't have said it better myself.*

# License

Unless otherwise noted, the NATS Core source files are distributed under the BSD 3-clause license found in the [LICENSE](https://github.com/drew-herron/nats.lv/blob/main/LICENSE) file.

# Acknowledgements

Thanks to everyone that publishes LabVIEW libraries for public use.
