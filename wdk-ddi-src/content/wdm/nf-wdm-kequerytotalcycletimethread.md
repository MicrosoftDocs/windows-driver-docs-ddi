---
UID: NF:wdm.KeQueryTotalCycleTimeThread
title: KeQueryTotalCycleTimeThread function (wdm.h)
description: The KeQueryTotalCycleTimeThread routine returns the accumulated cycle time for the specified thread.
old-location: kernel\kequerytotalcycletimethread_.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["KeQueryTotalCycleTimeThread function"]
ms.keywords: KeQueryTotalCycleTimeThread, KeQueryTotalCycleTimeThread , KeQueryTotalCycleTimeThread routine [Kernel-Mode Driver Architecture], kernel.kequerytotalcycletimethread_, wdm/KeQueryTotalCycleTimeThread
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KeQueryTotalCycleTimeThread
 - wdm/KeQueryTotalCycleTimeThread
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - KeQueryTotalCycleTimeThread
---

# KeQueryTotalCycleTimeThread function


## -description

The <b>KeQueryTotalCycleTimeThread</b> routine returns the accumulated cycle time for the specified thread.

## -parameters

### -param Thread [in, out]


A pointer to a dispatcher object of type KTHREAD.

### -param CycleTimeStamp [out]


A pointer to the cycle counter value at the time of the query.

## -returns

The accumulated cycle time for the thread.

