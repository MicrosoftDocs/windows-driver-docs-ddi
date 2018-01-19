---
UID: NS:ntddk._SOC_SUBSYSTEM_FAILURE_DETAILS
title: _SOC_SUBSYSTEM_FAILURE_DETAILS
author: windows-driver-content
description: The SOC_SUBSYSTEM_FAILURE_DETAILS structure holds information related to a System on a Chip (SoC) bug code.
old-location: whea\soc_subsystem_failure_details.htm
old-project: whea
ms.assetid: 416F9A0C-0A86-4FAA-9052-5D37D29C464D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _SOC_SUBSYSTEM_FAILURE_DETAILS, *PSOC_SUBSYSTEM_FAILURE_DETAILS, SOC_SUBSYSTEM_FAILURE_DETAILS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SOC_SUBSYSTEM_FAILURE_DETAILS
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
req.irql: PASSIVE_LEVEL
req.typenames: *PSOC_SUBSYSTEM_FAILURE_DETAILS, SOC_SUBSYSTEM_FAILURE_DETAILS
---

# _SOC_SUBSYSTEM_FAILURE_DETAILS structure



## -description
The   <b>SOC_SUBSYSTEM_FAILURE_DETAILS</b> structure holds information related to a System on a Chip (SoC) bug code.

These bug codes store information in a 
  this structure.



## -syntax

````
typedef struct _SOC_SUBSYSTEM_FAILURE_DETAILS {
  SOC_SUBSYSTEM_TYPE SubsysType;
  ULONG64            FirmwareVersion;
  ULONG64            HardwareVersion;
  ULONG              UnifiedFailureRegionSize;
  CHAR               UnifiedFailureRegion[1];
} SOC_SUBSYSTEM_FAILURE_DETAILS, *PSOC_SUBSYSTEM_FAILURE_DETAILS;
````


## -struct-fields

### -field SubsysType

A value in the <a href="..\ntddk\ne-ntddk-_soc_subsystem_type.md">SOC_SYBSYSTEM_TYPE</a> enumeration or a vendor-defined subsystem type. Subsystem types in the range 0x10000 through 0x80000000 are reserved for independent hardware vendors. 


### -field FirmwareVersion

A vendor-defined SoC firmware version number.


### -field HardwareVersion

A  vendor-defined SoC hardware version number.


### -field UnifiedFailureRegionSize

The size, in bytes, of the <b>UnifiedFailureRegion</b> string including the <b>NULL</b> terminator.


### -field UnifiedFailureRegion

A null-terminated string, defined by the vendor, that  contains classification details about the error that occurred.


## -remarks
