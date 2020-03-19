---
UID: NF:fltkernel.FltPropagateIrpExtension
title: FltPropagateIrpExtension function (fltkernel.h)
description: The FltPropagateIrpExtension routine copies the IRP extension from one minifilter's callback data to another's callback data.
tech.root: ifsk
ms.assetid: d74bc90e-5118-49ea-8aab-70d172eb0196
ms.date: 01/02/2020
keywords: ["FltPropagateIrpExtension function"]
ms.keywords: FltPropagateIrpExtension, FltPropagateIrpExtension routine, fltkernel/FltPropagateIrpExtension
f1_keywords:
 - "fltkernel/FltPropagateIrpExtension"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10 version 1607.
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltPropagateIrpExtension
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltPropagateIrpExtension function

## -description

The **FltPropagateIrpExtension** routine copies the IRP extension from one minifilter's callback data to another's callback data.

## -parameters

### -param SourceData [in]

Pointer to the callback data context from which to copy the extension data.

### -param TargetData [in/out]

Pointer to the callback data context in which to copy the extension data.

### -param Flags [in]

Reserved; must be set to 0.

## -returns

**FltPropagateIrpExtension** returns STATUS_SUCCESS upon successful completion; otherwise, it returns one of the following **NTSTATUS** error values.

| Return code | Description |
| ----------- | ----------- |
| STATUS_INVALID_PARAMETER | *SourceData* or *TargetData* are not an IRP operation. |
| STATUS_INSUFFICIENT_RESOURCES | Could not allocate an extension in the target callback data. |

## -remarks

**FltPropagateIrpExtension** copies only those portions of the IRP extension data that are present.

## -see-also

[**FltFlushBuffers2**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltflushbuffers2)
