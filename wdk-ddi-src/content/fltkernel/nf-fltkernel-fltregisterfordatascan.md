---
UID: NF:fltkernel.FltRegisterForDataScan
title: FltRegisterForDataScan function (fltkernel.h)
description: The FltRegisterForDataScan routine enables data scanning for the volume attached to the minifilter instance.
old-location: ifsk\fltregisterfordatascan.htm
tech.root: ifsk
ms.assetid: E603975A-B927-475A-9DEA-2D01C1249819
ms.date: 05/24/2019
ms.keywords: FltRegisterForDataScan, FltRegisterForDataScan routine [Installable File System Drivers], fltkernel/FltRegisterForDataScan, ifsk.fltregisterfordatascan
ms.topic: function
f1_keywords:
 - "fltkernel/FltRegisterForDataScan"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltRegisterForDataScan routine is available starting with   Windows 8.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltRegisterForDataScan
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltRegisterForDataScan function

## -description

The **FltRegisterForDataScan** routine enables data scanning for the volume attached to the minifilter instance.

## -parameters

### -param Instance [in]

An opaque instance pointer for the minifilter driver instance to register for data scanning.

## -returns

**FltRegisterForDataScan** returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following.

| Return code | Description |
| ----------- | ----------- |
| **STATUS_NOT_SUPPORTED** | The filter manager does not support data scans for the volume attached to this instance. |

## -remarks

A minifilter that does data scanning must register its volume for scanning by calling **FltRegisterForDataScan** prior to calling  [FltCreateSectionForDataScan](nf-fltkernel-fltcreatesectionfordatascan.md). Minifilters do data scans for various reasons, such as virus detection, encryption, or compression.

If **FltRegisterForDataScan** returns **STATUS_NOT_SUPPORTED**, a minifilter can still create sections for data scanning using [FsRtlCreateSectionForDataScan](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlcreatesectionfordatascan). However, section access is not synchronized and conflict resolution is left to the minifilter driver through its [PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK](nc-fltkernel-pflt_section_conflict_notification_callback.md) callback routine.

## -see-also

[FltAllocateContext](nf-fltkernel-fltallocatecontext.md)

[FltCloseSectionForDataScan](nf-fltkernel-fltclosesectionfordatascan.md)

[FltCreateSectionForDataScan](nf-fltkernel-fltcreatesectionfordatascan.md)

[FsRtlCreateSectionForDataScan](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlcreatesectionfordatascan)

[PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK](nc-fltkernel-pflt_section_conflict_notification_callback.md)
