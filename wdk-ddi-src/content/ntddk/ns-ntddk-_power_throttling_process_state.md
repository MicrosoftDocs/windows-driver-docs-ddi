---
UID: NS:ntddk._POWER_THROTTLING_PROCESS_STATE
title: "_POWER_THROTTLING_PROCESS_STATE"
author: windows-driver-content
description: Stores the throttling policies and how to apply them to a target process when that process is subject to power management.
old-location: kernel\power_throttling_process_state.htm
tech.root: kernel
ms.assetid: f22be66a-1f1c-4999-a99e-9a8575313239
ms.date: 04/30/2018
ms.keywords: "*PPOWER_THROTTLING_PROCESS_STATE, POWER_THROTTLING_PROCESS_STATE, POWER_THROTTLING_PROCESS_STATE structure [Kernel-Mode Driver Architecture], _POWER_THROTTLING_PROCESS_STATE, kernel.power_throttling_process_state, ntddk/POWER_THROTTLING_PROCESS_STATE"
ms.topic: struct
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddk.h
api_name:
-	POWER_THROTTLING_PROCESS_STATE
product:
- Windows
targetos: Windows
req.typenames: POWER_THROTTLING_PROCESS_STATE, *PPOWER_THROTTLING_PROCESS_STATE
---

# _POWER_THROTTLING_PROCESS_STATE structure


## -description


Stores the throttling policies and how to apply them to a target process when that process is subject to power management.


## -struct-fields




### -field Version

The version of this structure. Set to PROCESS_POWER_THROTTLING_CURRENT_VERSION.


### -field ControlMask

Flags that enable the caller to take control of the power throttling mechanism.

<ul>
<li>PROCESS_POWER_THROTTLING_EXECUTION_SPEED: Manages the execution speed of the process.</li>
</ul>

### -field StateMask

Flags that manage the power throttling mechanism on/off state.

<ul>
<li>PROCESS_POWER_THROTTLING_EXECUTION_SPEED: Manages the execution speed of the process.</li>
</ul>
