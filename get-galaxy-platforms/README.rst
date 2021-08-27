get-galaxy-platforms
====================

Ansible Galaxy doesn't have a way to easily retrieve all the available platforms
and versions for tagging Ansible role metadata properly.

See GitHub issues:

- https://github.com/ansible/galaxy-issues/issues/256
- https://github.com/ansible/galaxy/issues/52

This short script queries the API, handles the pagination and returns a simple
dictionary containing the names and versions.

It looks like this (at the moment of writing)::

    $ get-galaxy-platforms.py
    {
      "AIX": {
        "name": "AIX",
        "versions": [
          "6.1",
          "7.1",
          "7.2"
        ]
      },
      "Alpine": {
        "name": "Alpine",
        "versions": [
          "any"
        ]
      },
      "Amazon": {
        "name": "Amazon",
        "versions": [
          "2013.03",
          "2013.09",
          "2014.03",
          "2014.09",
          "2015.03",
          "2015.09",
          "2016.03",
          "2016.09",
          "2017.03",
          "2017.09",
          "2017.12",
          "2018.03",
          "Candidate"
        ]
      },
      "Amazon Linux 2": {
        "name": "Amazon Linux 2",
        "versions": [
          "any"
        ]
      },
      "aos": {
        "name": "aos",
        "versions": [
          "any"
        ]
      },
      "ArchLinux": {
        "name": "ArchLinux",
        "versions": [
          "any"
        ]
      },
      "ClearLinux": {
        "name": "ClearLinux",
        "versions": [
          "any"
        ]
      },
      "Cumulus": {
        "name": "Cumulus",
        "versions": [
          "2.5",
          "3.0",
          "3.1",
          "3.2",
          "3.3",
          "3.4",
          "3.5"
        ]
      },
      "Debian": {
        "name": "Debian",
        "versions": [
          "bullseye",
          "buster",
          "etch",
          "jessie",
          "lenny",
          "sid",
          "squeeze",
          "stretch",
          "wheezy"
        ]
      },
      "DellOS": {
        "name": "DellOS",
        "versions": [
          "10",
          "6",
          "9"
        ]
      },
      "Devuan": {
        "name": "Devuan",
        "versions": [
          "ascii",
          "beowulf",
          "ceres",
          "jessie"
        ]
      },
      "DragonFlyBSD": {
        "name": "DragonFlyBSD",
        "versions": [
          "5.2",
          "5.4"
        ]
      },
      "EL": {
        "name": "EL",
        "versions": [
          "5",
          "6",
          "7",
          "8"
        ]
      },
      "eos": {
        "name": "eos",
        "versions": [
          "any"
        ]
      },
      "Fedora": {
        "name": "Fedora",
        "versions": [
          "16",
          "17",
          "18",
          "19",
          "20",
          "21",
          "22",
          "23",
          "24",
          "25",
          "26",
          "27",
          "28",
          "29",
          "30",
          "31",
          "32"
        ]
      },
      "FreeBSD": {
        "name": "FreeBSD",
        "versions": [
          "10.0",
          "10.1",
          "10.2",
          "10.3",
          "10.4",
          "11.0",
          "11.1",
          "11.2",
          "11.3",
          "12.0",
          "12.1",
          "8.0",
          "8.1",
          "8.2",
          "8.3",
          "8.4",
          "9.0",
          "9.1",
          "9.2",
          "9.3"
        ]
      },
      "GenericBSD": {
        "name": "GenericBSD",
        "versions": [
          "any"
        ]
      },
      "GenericLinux": {
        "name": "GenericLinux",
        "versions": [
          "any"
        ]
      },
      "GenericUNIX": {
        "name": "GenericUNIX",
        "versions": [
          "any"
        ]
      },
      "Gentoo": {
        "name": "Gentoo",
        "versions": [
          "any"
        ]
      },
      "HardenedBSD": {
        "name": "HardenedBSD",
        "versions": [
          "10",
          "11"
        ]
      },
      "IOS": {
        "name": "IOS",
        "versions": [
          "any"
        ]
      },
      "Junos": {
        "name": "Junos",
        "versions": [
          "any"
        ]
      },
      "macOS": {
        "name": "macOS",
        "versions": [
          "Big-Sur",
          "High-Sierra",
          "Sierra"
        ]
      },
      "MacOSX": {
        "name": "MacOSX",
        "versions": [
          "10.10",
          "10.11",
          "10.12",
          "10.13",
          "10.14",
          "10.15",
          "10.7",
          "10.8",
          "10.9"
        ]
      },
      "NXOS": {
        "name": "NXOS",
        "versions": [
          "any"
        ]
      },
      "OpenBSD": {
        "name": "OpenBSD",
        "versions": [
          "5.6",
          "5.7",
          "5.8",
          "5.9",
          "6.0",
          "6.1",
          "6.2",
          "6.3",
          "6.4",
          "6.5",
          "6.6",
          "6.7"
        ]
      },
      "opensuse": {
        "name": "opensuse",
        "versions": [
          "12.1",
          "12.2",
          "12.3",
          "13.1",
          "13.2",
          "15.0",
          "15.1",
          "15.2",
          "42.1",
          "42.2",
          "42.3"
        ]
      },
      "os10": {
        "name": "os10",
        "versions": [
          "all",
          "any"
        ]
      },
      "PAN-OS": {
        "name": "PAN-OS",
        "versions": [
          "7.1",
          "8.0",
          "8.1",
          "9.0"
        ]
      },
      "SLES": {
        "name": "SLES",
        "versions": [
          "10SP3",
          "10SP4",
          "11",
          "11SP1",
          "11SP2",
          "11SP3",
          "11SP4",
          "12",
          "12SP1",
          "15"
        ]
      },
      "SmartOS": {
        "name": "SmartOS",
        "versions": [
          "any"
        ]
      },
      "Solaris": {
        "name": "Solaris",
        "versions": [
          "10",
          "11.0",
          "11.1",
          "11.2",
          "11.3"
        ]
      },
      "Synology": {
        "name": "Synology",
        "versions": [
          "any"
        ]
      },
      "TMOS": {
        "name": "TMOS",
        "versions": [
          "12.1",
          "13.0",
          "13.1",
          "14.0"
        ]
      },
      "Ubuntu": {
        "name": "Ubuntu",
        "versions": [
          "artful",
          "bionic",
          "cosmic",
          "cuttlefish",
          "disco",
          "eoan",
          "focal",
          "groovy",
          "lucid",
          "maverick",
          "natty",
          "oneiric",
          "precise",
          "quantal",
          "raring",
          "saucy",
          "trusty",
          "utopic",
          "vivid",
          "wily",
          "xenial",
          "yakkety",
          "zesty"
        ]
      },
      "vCenter": {
        "name": "vCenter",
        "versions": [
          "5.5",
          "6.0",
          "6.5",
          "6.7"
        ]
      },
      "Void Linux": {
        "name": "Void Linux",
        "versions": [
          "any"
        ]
      },
      "vSphere": {
        "name": "vSphere",
        "versions": [
          "5.5",
          "6.0",
          "6.5",
          "6.7"
        ]
      },
      "Windows": {
        "name": "Windows",
        "versions": [
          "2008R2",
          "2008x64",
          "2008x86",
          "2012",
          "2012R2",
          "2016",
          "2019"
        ]
      }
    }
