---
UID: NF:fltkernel.FltPropagateActivityIdToThread
title: FltPropagateActivityIdToThread function (fltkernel.h)
description: The FltPropagateActivityIdToThread routine associates the activity ID from the IRP in the minifilter's callback data with the current thread.
old-location: ifsk\fltpropagateactivityidtothread.htm
tech.root: ifsk
ms.assetid: 7453EEB1-F974-4AEB-93C4-A75A79E1FE19
ms.date: 04/16/2018
keywords: ["FltPropagateActivityIdToThread function"]
ms.keywords: FltPropagateActivityIdToThread, FltPropagateActivityIdToThread routine [Installable File System Drivers], fltkernel/FltPropagateActivityIdToThread, ifsk.fltpropagateactivityidtothread
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FltPropagateActivityIdToThread
 - fltkernel/FltPropagateActivityIdToThread
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltPropagateActivityIdToThread
---

# FltPropagateActivityIdToThread function

## -description

The **FltPropagateActivityIdToThread** routine associates the activity ID from the  IRP in the minifilter's callback data with the current thread.

## -parameters

### -param CallbackData

[in] Pointer to the callback data containing the request with an associated activity ID.

### -param PropagateId

[in/out] Pointer to a caller allocated **GUID** that stores the activity ID for the current thread.

### -param OriginalId

[out] On return, the **GUID** pointer referenced by **OriginalId** points to the activity ID that was previously set for the thread.

## -returns

**FltPropagateActivityIdToThread** returns one of the following **NTSTATUS** values.

| Return code | Description |
| ----------- | ----------- |
| STATUS_NOT_SUPPORTED | The callback data does not contain a request for an IRP operation. |
| STATUS_NOT_FOUND | No activity ID is associated with the request in **CallbackData**. |
| STATUS_SUCCESS | An activity ID was returned in the **GUID** value pointed to by **OriginalId**. |

## -remarks

The **FltPropagateActivityIdToThread** routine is used by trace aware minifilters. A minifilter uses this routine to attach the activity ID from an IRP to a worker thread processing I/O for the request.

A minifilter must call **IoClearActivityIdThread** with the pointer in **OriginalId** before returning control from the worker thread if the call to **FltPropagateActivityIdToThread** was successful.

## -see-also

[**FltGetActivityIdCallbackData**](nf-fltkernel-fltgetactivityidcallbackdata.md)

[**FltSetActivityIdCallbackData**](nf-fltkernel-fltsetactivityidcallbackdata.md)
