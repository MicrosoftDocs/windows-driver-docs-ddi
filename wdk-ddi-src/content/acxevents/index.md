---
UID: NA:acxevents
title: acxevents.h header
ms.date: 11/04/2021
description: The  acxevents.h header is used by the ACX audio class extensions.
keywords: ["acxevents.h header"]
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
tech.root: audio
f1_keywords:
 - acxevents
 - acxevents/acxevents
api_name:
 - acxevents
---

# acxevents.h header

The acxevents header is used by the ACX audio class extensions.

An AcxEvent represents an asynchronous notification available at the driver level. Events can be added to AcxCircuits, AcxStreams, AcxElements and AcxPins. Internally, they are exposed as KS events to upper layers. 

TBD - It would be good to discuss when you would want to use acx events and for what purpose.

For more information, see:

- [ACX Audio Class Extensions overview](/windows-hardware/drivers/audio/acx-audio-class-extensions-overview)
 
- [Audio](../_audio/index.md)

## Audio Kernel Steaming KSEVENTS

For general information on KSEVENTS, see these topics.

[KS Events](/windows-hardware/drivers/stream/ks-events)
[KSEVENT structure](/windows-hardware/drivers/stream/ksevent-structure)
[KSPROPSETID_Audio](/windows-hardware/drivers/audio/kspropsetid-audio)

TBD - Need to confirm these all map to ACX?

[Audio Device Hardware Events](/windows-hardware/drivers/audio/hardware-events)


## Header elements

acxevents.h contains the following programming interfaces:

