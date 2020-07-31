---
UID: NS:ntddk._POWER_THROTTLING_THREAD_STATE
title: _POWER_THROTTLING_THREAD_STATE (ntddk.h)
description: Stores the throttling policies and how to apply them to a target thread when that thread is subject to power management.
old-location: kernel\power_throttling_thread_state.htm
tech.root: kernel
ms.assetid: 85659694-f93a-42dc-9fa4-f6fea6ad71d0
ms.date: 04/30/2018
keywords: ["_POWER_THROTTLING_THREAD_STATE structure"]
ms.keywords: "*PPOWER_THROTTLING_THREAD_STATE, POWER_THROTTLING_THREAD_STATE, POWER_THROTTLING_THREAD_STATE structure [Kernel-Mode Driver Architecture], _POWER_THROTTLING_THREAD_STATE, kernel.power_throttling_thread_state, ntddk/POWER_THROTTLING_THREAD_STATE"
f1_keywords:
 - "ntddk/POWER_THROTTLING_THREAD_STATE"
 - "POWER_THROTTLING_THREAD_STATE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddk.h
api_name:
- POWER_THROTTLING_THREAD_STATE
targetos: Windows
req.typenames: POWER_THROTTLING_THREAD_STATE, *PPOWER_THROTTLING_THREAD_STATE
---

# _POWER_THROTTLING_THREAD_STATE structure


## -description


Stores the throttling policies and how to apply them to a target thread when that thread is subject to power management.


## -struct-fields




### -field Version

The version of this structure. Set to THREAD_POWER_THROTTLING_CURRENT_VERSION.


### -field ControlMask

Flags that enable the caller to take control of the power throttling mechanism.

<ul>
<li>THREAD_POWER_THROTTLING_EXECUTION_SPEED: Manages the execution speed of the process.</li>
</ul>

### -field StateMask

Flags that manage the power throttling mechanism on/off state.

<ul>
<li>THREAD_POWER_THROTTLING_EXECUTION_SPEED: Manages the execution speed of the process.</li>
</ul>
