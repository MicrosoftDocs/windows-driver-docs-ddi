---
UID: NE:portcls._PC_EXIT_LATENCY
title: _PC_EXIT_LATENCY (portcls.h)
description: This topic discusses the PC_EXIT_LATENCY enum, and describes its members. The latency times map to specific maximum times in which the device must be able to exit its sleep state and enter the fully functional state (D0).
old-location: audio\pc_exit_latency.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["PC_EXIT_LATENCY enumeration"]
ms.keywords: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY, PC_EXIT_LATENCY enumeration [Audio Devices], PcExitLatencyFast, PcExitLatencyInstant, PcExitLatencyResponsive, _PC_EXIT_LATENCY, audio.pc_exit_latency, portcls/PC_EXIT_LATENCY, portcls/PcExitLatencyFast, portcls/PcExitLatencyInstant, portcls/PcExitLatencyResponsive"
req.header: portcls.h
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
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
f1_keywords:
 - _PC_EXIT_LATENCY
 - portcls/_PC_EXIT_LATENCY
 - PPC_EXIT_LATENCY
 - portcls/PPC_EXIT_LATENCY
 - PC_EXIT_LATENCY
 - portcls/PC_EXIT_LATENCY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Portcls.h
api_name:
 - PC_EXIT_LATENCY
---

# _PC_EXIT_LATENCY enumeration


## -description

This topic discusses the PC_EXIT_LATENCY enum, and describes its members. The latency times map to specific maximum times in which the device must be able to exit its sleep state and enter the fully functional state (D0).

## -enum-fields

### -field PcExitLatencyInstant

Indicates a 0-millisecond latency. This means "Do not power down" and it  will only be sent when a device is in the D0 state.

### -field PcExitLatencyFast

Indicates a 35-millisecond resume latency.

### -field PcExitLatencyResponsive

Indicates a 300-millisecond resume latency.

