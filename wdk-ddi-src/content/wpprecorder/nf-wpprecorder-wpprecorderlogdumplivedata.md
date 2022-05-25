---
UID: NF:wpprecorder.WppRecorderLogDumpLiveData
tech.root: devtest
title: WppRecorderLogDumpLiveData
ms.date: 04/21/2022
targetos: Windows
description: The WppRecorderLogDumpLiveData method returns an opaque pointer to a log buffer header and data so that they can be saved in a live crashdump.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wpprecorder.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wpprecorder.h
api_name:
 - WppRecorderLogDumpLiveData
f1_keywords:
 - WppRecorderLogDumpLiveData
 - wpprecorder/WppRecorderLogDumpLiveData
dev_langs:
 - c++
helpviewer_keywords:
 - WppRecorderLogDumpLiveData
---

## -description

The **WppRecorderLogDumpLiveData** method returns an opaque pointer to a log buffer header and data so that they can be saved in a live crashdump.

## -syntax

```cpp
__drv_maxIRQL(HIGH_LEVEL)
NTSTATUS
WppRecorderLogDumpLiveData(
    _In_
        RECORDER_LOG         RecorderLog,
    _Out_ __deref_ecount(*OutBufferLength)
        PVOID              * OutBuffer,
    _Out_
        PULONG               OutBufferLength,
    _Out_
        LPGUID               Guid
    );
```

## -parameters

### -param RecorderLog [in]

A recorder log handle returned in a previous call to [**WppRecorderLogCreate**](/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderlogcreate) or [**WppRecorderLogGetDefault**](/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-imp_wpprecorderloggetdefault).

### -param OutBuffer [out]

Pointer to the beginning of the combined header and log buffer.

### -param OutBufferLength [out]

Pointer to a ULONG that contains the length of the combined data.

### -param Guid [out]

Reserved.

## -remarks

Returns STATUS_SUCCESS if the operation succeeds. If not successful, the out parameters are invalid.

## -see-also
