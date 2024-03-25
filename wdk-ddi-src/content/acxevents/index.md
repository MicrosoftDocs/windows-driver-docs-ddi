---
UID: NA:acxevents
title: acxevents.h header
ms.date: 11/10/2023
description: The  acxevents.h header is used by an ACX audio class extensions.
keywords: ["acxevents.h header"]
ms.keywords: 
ms.service: windows-hardware-driver-quality
ms.subservice: windows-devices
ms.topic: overview
tech.root: audio
f1_keywords:
 - acxevents
 - acxevents/acxevents
api_name:
 - acxevents
---

# acxevents.h header

## -description

The acxevents header is used by the ACX audio class extensions.

An ACXEVENT represents an asynchronous notification available at the driver level. Events can be added to ACXCIRCUITs, ACXSTREAMs, ACXELEMENTs and ACXPINs. Internally, they are exposed as KS events to upper layers.

ACXEVENTs can be used for a variety of purposes, for example they can be used to signal user caused hardware events. Some audio devices provide hardware volume-control knobs, mute switches, or other types of manual controls. Applications can respond to changes in these controls by adjusting the volume or otherwise changing the way that the audio stream is played. When the user adjusts a hardware control, ACX informs the driver that a hardware event has occurred.

For more information, see:

- [ACX Audio Class Extensions overview](/windows-hardware/drivers/audio/acx-audio-class-extensions-overview)

- [Audio](../_audio/index.md)

**Audio Kernel Steaming KSEVENTS**

For general information on KSEVENTS, see these topics.

[KS Events](/windows-hardware/drivers/stream/ks-events)

[KSEVENT structure](/windows-hardware/drivers/stream/ksevent-structure)

[KSPROPSETID_Audio](/windows-hardware/drivers/audio/kspropsetid-audio)

[Audio Device Hardware Events](/windows-hardware/drivers/audio/hardware-events)

>[!NOTE]
> The ACX headers and libraries are not included in the  WDK 10.0.22621.2428 (released October 24, 2023), but are available in previous versions, as well as the latest (25000 series builds) Insider Preview of the WDK. For more information about preview versions of the WDK, see [Installing preview versions of the Windows Driver Kit (WDK)](/windows-hardware/drivers/installing-preview-versions-wdk).
