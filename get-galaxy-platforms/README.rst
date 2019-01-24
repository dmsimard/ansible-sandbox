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
        "2016.03",
        "2016.09",
        "2017.03",
        "2017.09",
        "2017.12",
        "Candidate"
        ]
    },
    "ArchLinux": {
        "name": "ArchLinux",
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
    "EL": {
        "name": "EL",
        "versions": [
        "5",
        "6",
        "7"
        ]
    },
    "eos": {
        "name": "eos",
        "versions": [
        "Any"
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
        "29"
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
        "6.3"
        ]
    },
    "opensuse": {
        "name": "opensuse",
        "versions": [
        "12.1",
        "12.2",
        "12.3",
        "13.1",
        "13.2"
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
        "12SP1"
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
        "2016"
        ]
    }
    }