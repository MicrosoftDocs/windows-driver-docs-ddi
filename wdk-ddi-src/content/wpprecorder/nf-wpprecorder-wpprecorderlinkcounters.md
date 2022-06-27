---
UID: NF:wpprecorder.WppRecorderLinkCounters
title: WppRecorderLinkCounters macro (wpprecorder.h)
description: Learn how the WppRecorderLinkCounters method uses a sequence number to merge logs captured in different buffers by a driver.
old-location: devtest\wpprecorderlinkcounters.htm
tech.root: devtest
ms.date: 04/19/2022
keywords: ["WppRecorderLinkCounters macro"]
ms.keywords: WppRecorderLinkCounters, devtest.wpprecorderlinkcounters, imp_WppRecorderLinkCounters, imp_WppRecorderLinkCounters function [Driver Development Tools], wpprecorder/imp_WppRecorderLinkCounters
req.header: wpprecorder.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
 - WppRecorderLinkCounters
 - wpprecorder/WppRecorderLinkCounters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wpprecorder.h
api_name:
 - WppRecorderLinkCounters
---

# WppRecorderLinkCounters macro


## -description

The <b>WppRecorderLinkCounters</b> method  uses a sequence number to merge logs captured in different buffers by a driver.

## -syntax

```cpp
__drv_maxIRQL(DISPATCH_LEVEL)
NTSTATUS
WppRecorderLinkCounters(
    _In_
        WPP_RECORDER_COUNTER        CounterOwner
    );
```

## -parameters

### -param CounterOwner [in]


ID of the counter whose current value is to be read.

## -remarks

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, one of appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> values
