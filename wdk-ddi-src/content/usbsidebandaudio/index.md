---
description: "The Usbsidebandaudio.h defines the types, constants, and functions that are exposed to device drivers that interact with the Windows USB Audio Driver for Sideband Audio."
UID: NA:usbsidebandaudio
title: Usbsidebandaudio.h header
ms.assetid: a245e760-fd7d-3efa-9b5f-09303bd40240
ms.date: 06/30/2023
keywords: ["Usbsidebandaudio.h header"]
ms.keywords: 
ms.topic: reference
tech.root: audio
f1_keywords:
 - usbsidebandaudio
 - usbsidebandaudio/usbsidebandaudio
api_name:
 - usbsidebandaudio
---

# Usbsidebandaudio.h header

## -description

The header defines the types, constants, and functions that are exposed to device drivers that interact with the Windows USB Audio Driver for Sideband Audio.

Audio drivers that want to provide Sideband path for USB Audio 1.0 devices should wait for Pnp notification for the Sideband interface to be published by the USB Audio 1.0 class driver - `GUID_DEVINTERFACE_USB_SIDEBAND_AUDIO_HS_HCIBYPASS`.

When Audio driver receives Pnp notification, it can use the symbolic link to send I/O and interact with the USB Audio 1.0 class device.

The IOCTLs are specified in the [sidebandaudio.h](../sidebandaudio/index.md) header for all standard Sideband Audio operations.

USB Audio 1.0 specific structures and enums are defined in this header.

For more information, see:

[Audio](../_audio/index.md)
