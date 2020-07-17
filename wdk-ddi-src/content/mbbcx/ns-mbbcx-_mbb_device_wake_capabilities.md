---
UID: NS:mbbcx._MBB_DEVICE_WAKE_CAPABILITIES
title: MBB_DEVICE_WAKE_CAPABILITIES (mbbcx.h)
author: windows-driver-content
description: The MBB_DEVICE_WAKE_CAPABILITIES structure describes a MBBCx net adapter's wake-on-LAN (WoL) capabilities.
tech.root: netvista
ms.assetid: a366fb3b-30b7-4abf-9619-5580707673ce
ms.author: windowsdriverdev
ms.date: 11/07/2019
keywords: ["MBB_DEVICE_WAKE_CAPABILITIES structure"]
f1_keywords:
 - "mbbcx/MBB_DEVICE_WAKE_CAPABILITIES"
 - "MBB_DEVICE_WAKE_CAPABILITIES"
ms.keywords: MBB_DEVICE_WAKE_CAPABILITIES, MBB_DEVICE_WAKE_CAPABILITIES, 
req.header: mbbcx.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: MBB_DEVICE_WAKE_CAPABILITIES
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - mbbcx.h
api_name: 
 - MBB_DEVICE_WAKE_CAPABILITIES
product: 
 - Windows
targetos: Windows
ms.custom: Vb
---

# MBB_DEVICE_WAKE_CAPABILITIES structure

## -description

The **MBB_DEVICE_WAKE_CAPABILITIES** structure describes a MBBCx net adapter's wake-on-LAN (WoL) capabilities.

## -struct-fields

### -field Size

The size of this structure, in bytes.
 
### -field RegisterState

A boolean value indicating if the net adapter can generate wake-up events if its registration state with the mobile broadband service has changed.
 
### -field SmsReceive

A boolean value indicating if the net adapter can generate wake-up events if it recieves a Short Message Service (SMS) message that it must report to the mobile broadband service.
 
### -field UssdReceive

A boolean value indicating if the net adapter can generate wake-up events if it receives an Unstructured Supplementary Service Data (USSD) message.
 
### -field PacketState

A boolean value indicating if the net adapter can generate wake-up events if a packet state changes.
 
### -field UiccChange
 
A boolean value indicating if the net adapter can generate wake-up events if the SIM card state changes.

## -remarks

Call [**MBB_DEVICE_WAKE_CAPABILITIES_INIT**](../mbbcx/nf-mbbcx-mbb_device_wake_capabilities_init.md) to initialize this structure. An initialized **MBB_DEVICE_WAKE_CAPABILITIES** structure is passed as an input method to [**MbbDeviceSetWakeCapabilities**](../mbbcx/nf-mbbcx-mbbdevicesetwakecapabilities.md).

## -see-also
