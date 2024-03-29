---
UID: NC:wdm.KSTART_ROUTINE
title: KSTART_ROUTINE (wdm.h)
description: The ThreadStart routine provides an entry point for a driver-created system thread.
old-location: kernel\threadstart.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["KSTART_ROUTINE callback function"]
ms.keywords: DrvrRtns_913b72f4-9f6b-4967-879d-c4e565d219dd.xml, KSTART_ROUTINE, ThreadStart, ThreadStart routine [Kernel-Mode Driver Architecture], kernel.threadstart, wdm/ThreadStart
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 2000.
req.target-min-winversvr: 
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
req.irql: Called at PASSIVE_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - KSTART_ROUTINE
 - wdm/KSTART_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - KSTART_ROUTINE
---

# KSTART_ROUTINE callback function


## -description

The <i>ThreadStart</i> routine provides an entry point for a driver-created system thread.

## -parameters

### -param StartContext [in]


A caller-supplied pointer to driver-defined context information that is specified in the <i>StartContext</i> parameter a previous call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pscreatesystemthread">PsCreateSystemThread</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pscreatesystemthread">PsCreateSystemThread</a>

