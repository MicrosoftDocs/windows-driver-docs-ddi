---
UID: NF:fltkernel.FltRegisterForDataScan
title: FltRegisterForDataScan function (fltkernel.h)
description: The FltRegisterForDataScan routine enables data scanning for the volume attached to the minifilter instance.
old-location: ifsk\fltregisterfordatascan.htm
tech.root: ifsk
ms.date: 06/01/2022
keywords: ["FltRegisterForDataScan function"]
ms.keywords: FltRegisterForDataScan, FltRegisterForDataScan routine [Installable File System Drivers], fltkernel/FltRegisterForDataScan, ifsk.fltregisterfordatascan
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FltRegisterForDataScan
 - fltkernel/FltRegisterForDataScan
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltRegisterForDataScan
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
| STATUS_NOT_SUPPORTED | The filter manager does not support data scans for the volume attached to this instance. |

## -remarks

A minifilter that does data scanning must register its volume for scanning by calling **FltRegisterForDataScan** prior to calling  [**FltCreateSectionForDataScan**](nf-fltkernel-fltcreatesectionfordatascan.md). Minifilters do data scans for various reasons, such as virus detection, encryption, or compression.

> [!NOTE]
>
> If **FltRegisterForDataScan** returns STATUS_NOT_SUPPORTED, a minifilter can still create sections for data scanning by calling [**FsRtlCreateSectionForDataScan**](../ntifs/nf-ntifs-fsrtlcreatesectionfordatascan.md). However, access to the section created by **FsRtlCreateSectionForDataScan** is not synchronized, and it is the calling minifilter's responsibility to handle any conflict resolution that arises. Such a minifilter must implement and register a [**PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK**](nc-fltkernel-pflt_section_conflict_notification_callback.md) callback routine that can be called when section conflict occurs.

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltCloseSectionForDataScan**](nf-fltkernel-fltclosesectionfordatascan.md)

[**FltCreateSectionForDataScan**](nf-fltkernel-fltcreatesectionfordatascan.md)

[**FsRtlCreateSectionForDataScan**](../ntifs/nf-ntifs-fsrtlcreatesectionfordatascan.md)

[**PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK**](nc-fltkernel-pflt_section_conflict_notification_callback.md)
