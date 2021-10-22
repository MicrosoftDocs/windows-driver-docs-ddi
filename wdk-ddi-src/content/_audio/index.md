---
UID: TP:audio
title: Audio overview
ms.assetid: 91b97f1d-92f1-3c32-955a-dd6524d5b764
ms.date: 10/21/2021
description: This topic describes the headers that are used to create Microsoft Windows WDM and ACX audio drivers. These drivers control audio hardware that render and capture streams containing audio data.
keywords: ["Audio"]
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Audio

## -description

These headers are used to create Microsoft Windows Driver Model (WDM) audio drivers. These drivers control audio hardware that render and capture streams containing audio data.

To develop WDM portcls audio drivers, use these headers:

* [bthhfpddi.h](../bthhfpddi/index.md)
* [dmusicks.h](../dmusicks/index.md)
* [dmusprop.h](../dmusprop/index.md)
* [drmk.h](../drmk/index.md)
* [eventdetectoroemadapter.h](../eventdetectoroemadapter/index.md)
* [hdaudio.h](../hdaudio/index.md)
* [keyworddetectoroemadapter.h](../keyworddetectoroemadapter/index.md)
* [ksmedia.h](../ksmedia/index.md)
* [portcls.h](../portcls/index.md)

To develop audio class extension (ACX) drivers, use these headers:

* [acxcircuit.h](../acxcircuit/index.md)
* [acxdevice.h](../acxdevice/index.md)
* [acxdriver.h](../acxdriver/index.md)
* [acxelements.h](../acxelements/index.md)
* [acxevents.h](../acxevents/index.md)
* [acxpin.h](../acxpin/index.md)
* [acxstreams.h](../acxstreams/index.md)


For programming information, see [Audio Devices Design Guide](/windows-hardware/drivers/audio).
