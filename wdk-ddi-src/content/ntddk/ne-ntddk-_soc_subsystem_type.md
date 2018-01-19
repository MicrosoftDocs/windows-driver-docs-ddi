---
UID: NE:ntddk._SOC_SUBSYSTEM_TYPE
title: _SOC_SUBSYSTEM_TYPE
author: windows-driver-content
description: The SOC_SYBSYSTEM_TYPE enumeration defines different types of System on a Chip (SoC) subsystems.
old-location: whea\soc_sybsystem_type.htm
old-project: whea
ms.assetid: 179D61E3-C2EE-4821-93F8-DB763892DD3D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _SOC_SUBSYSTEM_TYPE, *PSOC_SUBSYSTEM_TYPE, SOC_SUBSYSTEM_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SOC_SUBSYSTEM_TYPE
req.alt-loc: ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: *PSOC_SUBSYSTEM_TYPE, SOC_SUBSYSTEM_TYPE
---

# _SOC_SUBSYSTEM_TYPE enumeration



## -description
The <b>SOC_SYBSYSTEM_TYPE</b> enumeration defines different types of System on a Chip (SoC) subsystems.

The <b>SybsysType</b> member of the <a href="..\ntddk\ns-ntddk-_soc_subsystem_failure_details.md">SOC_SUBSYSTEM_FAILURE_DETAILS</a> structure is a value from this enumeration. The <b>SOC_SUBSYSTEM_FAILURE_DETAILS</b> structure is used by these bug codes:



## -syntax

````
typedef enum _SOC_SUBSYSTEM_TYPE { 
  SOC_SUBSYSTEM_WIRELESS_MODEM     = 0,
  SOC_SUBSYS_AUDIO_DSP             = 1,
  SOC_SUBSYS_WIRELSS_CONNECTIVITY  = 2,
  SOC_SUBSYS_SENSORS               = 3,
  SOC_SUBSYS_VENDOR_DEFINED        = 0x10000
} SOC_SUBSYSTEM_TYPE;
````


## -enum-fields

### -field SOC_SUBSYSTEM_WIRELESS_MODEM

Wireless modem


### -field SOC_SUBSYS_AUDIO_DSP

Audio digital signal processor (DSP)


### -field SOC_SUBSYS_WIRELSS_CONNECTIVITY

Wireless connectivity


### -field SOC_SUBSYS_SENSORS

Sensors


### -field SOC_SUBSYS_VENDOR_DEFINED

Subsystem types in the range 0x10000 through 0x80000000 are reserved for independent hardware vendors.


## -remarks
