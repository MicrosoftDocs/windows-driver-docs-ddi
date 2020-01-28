---
UID: NE:ntddk._SOC_SUBSYSTEM_TYPE
title: _SOC_SUBSYSTEM_TYPE (ntddk.h)
description: The SOC_SYBSYSTEM_TYPE enumeration defines different types of System on a Chip (SoC) subsystems.
old-location: whea\soc_sybsystem_type.htm
tech.root: whea
ms.assetid: 179D61E3-C2EE-4821-93F8-DB763892DD3D
ms.date: 02/20/2018
ms.keywords: "*PSOC_SUBSYSTEM_TYPE, SOC_SUBSYSTEM_TYPE, SOC_SUBSYSTEM_TYPE enumeration [WHEA Drivers and Applications], SOC_SUBSYSTEM_WIRELESS_MODEM, SOC_SUBSYS_AUDIO_DSP, SOC_SUBSYS_SENSORS, SOC_SUBSYS_VENDOR_DEFINED, SOC_SUBSYS_WIRELSS_CONNECTIVITY, _SOC_SUBSYSTEM_TYPE, ntddk/SOC_SUBSYSTEM_TYPE, ntddk/SOC_SUBSYSTEM_WIRELESS_MODEM, ntddk/SOC_SUBSYS_AUDIO_DSP, ntddk/SOC_SUBSYS_SENSORS, ntddk/SOC_SUBSYS_VENDOR_DEFINED, ntddk/SOC_SUBSYS_WIRELSS_CONNECTIVITY, whea.soc_sybsystem_type"
f1_keywords:
 - "ntddk/SOC_SUBSYSTEM_TYPE"
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- SOC_SUBSYSTEM_TYPE
product:
- Windows
targetos: Windows
req.typenames: SOC_SUBSYSTEM_TYPE, *PSOC_SUBSYSTEM_TYPE
---

# _SOC_SUBSYSTEM_TYPE enumeration


## -description


The <b>SOC_SYBSYSTEM_TYPE</b> enumeration defines different types of System on a Chip (SoC) subsystems.

The <b>SybsysType</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_soc_subsystem_failure_details">SOC_SUBSYSTEM_FAILURE_DETAILS</a> structure is a value from this enumeration. The <b>SOC_SUBSYSTEM_FAILURE_DETAILS</b> structure is used by these bug codes:
<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-0x14b--soc-subsystem-failure">Bug Check 0x14B SOC_SUBSYSTEM_FAILURE</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-0x15d-soc-subsystem-failure-livedump">Bug Check 0x15D SOC_SUBSYSTEM_FAILURE_LIVEDUMP</a>
</li>
</ul>

## -enum-fields




### -field SOC_SUBSYS_WIRELESS_MODEM
Wireless modem.

### -field SOC_SUBSYS_AUDIO_DSP

Audio digital signal processor (DSP).


### -field SOC_SUBSYS_WIRELSS_CONNECTIVITY

Wireless connectivity.


### -field SOC_SUBSYS_SENSORS

Sensors.

### -field SOC_SUBSYS_COMPUTE_DSP : 
Compute digital signal processor (DSP).

### -field SOC_SUBSYS_VENDOR_DEFINED

Subsystem types in the range 0x10000 through 0x80000000 are reserved for independent hardware vendors.


#### - SOC_SUBSYSTEM_WIRELESS_MODEM

Wireless modem.

