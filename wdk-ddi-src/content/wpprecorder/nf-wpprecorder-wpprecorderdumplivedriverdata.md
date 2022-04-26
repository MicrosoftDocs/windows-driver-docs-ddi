---
UID: NF:wpprecorder.WppRecorderDumpLiveDriverData
title: WppRecorderDumpLiveDriverData macro (wpprecorder.h)
description: Learn how the WppRecorderDumpLiveDriverData method gets the buffer associated with the specified Inflight Trace Recorder log.
old-location: devtest\wpprecorderdumplivedriverdata.htm
tech.root: devtest
ms.date: 04/19/2022
keywords: ["WppRecorderDumpLiveDriverData macro"]
ms.keywords: WppRecorderDumpLiveDriverData, devtest.wpprecorderdumplivedriverdata, imp_WppRecorderDumpLiveDriverData, imp_WppRecorderDumpLiveDriverData function [Driver Development Tools], wpprecorder/imp_WppRecorderDumpLiveDriverData
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
 - WppRecorderDumpLiveDriverData
 - wpprecorder/WppRecorderDumpLiveDriverData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wpprecorder.h
api_name:
 - WppRecorderDumpLiveDriverData
---

# WppRecorderDumpLiveDriverData macro


## -description

The <a href="/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderdumplivedriverdata">WppRecorderDumpLiveDriverData</a> method gets the buffer associated with the specified Inflight Trace Recorder log.

## -syntax

```cpp
__drv_maxIRQL(HIGH_LEVEL)
NTSTATUS
WppRecorderDumpLiveDriverData(
    _Out_ __deref_ecount(*OutBufferLength)
        PVOID              * OutBuffer,
    _Out_
        PULONG               OutBufferLength,
    _Out_
        LPGUID               Guid
    );
```

## -parameters

### -param OutBuffer [out]

Pointer to the buffer that was allocated by WppRecorderLogCreate.

### -param OutBufferLength [out]

Pointer to a ULONG that contains the size of the output buffer pointed to by OutBuffer.

### -param Guid [out]

Pointer to the WPP controller GUID that identifies the driver data.

## -remarks

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, one of appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> values
