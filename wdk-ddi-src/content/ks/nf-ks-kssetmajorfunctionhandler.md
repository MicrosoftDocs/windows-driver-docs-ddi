---
UID: NF:ks.KsSetMajorFunctionHandler
title: KsSetMajorFunctionHandler function (ks.h)
description: The KsSetMajorFunctionHandler function sets the handler for a specified major function to use the internal dispatching.
old-location: stream\kssetmajorfunctionhandler.htm
tech.root: stream
ms.assetid: 22c1957d-089a-4504-b92c-9268a37ac265
ms.date: 04/23/2018
ms.keywords: KsSetMajorFunctionHandler, KsSetMajorFunctionHandler function [Streaming Media Devices], ks/KsSetMajorFunctionHandler, ksfunc_e8761f66-4ca5-4465-bf7b-f6d2ab1d2355.xml, stream.kssetmajorfunctionhandler
ms.topic: function
f1_keywords:
 - "ks/KsSetMajorFunctionHandler"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsSetMajorFunctionHandler
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsSetMajorFunctionHandler function

## -description

The **KsSetMajorFunctionHandler** function sets the handler for a specified major function to use the internal dispatching. It routes through a KSDISPATCH_TABLE contained in the opaque object header to be the first element within a structure pointed to by an **FsContext** within a file object. The dispatching assumes the table and **FsContext** structure are initialized by the device using **KsAllocateObjectHeader**.

## -parameters

### -param DriverObject [in]

Specifies the driver object whose major function is to be handled.

### -param MajorFunction [in]

Specifies the major function identifier to be handled. This sets the major function pointer in the driver object to an internal function that then dispatches to the **KSDISPATCH_TABLE** function. The pointer to this table is assumed to be the first element in a structure pointed to by **FsContext** in the file object of the specific IRP being dispatched. The valid major function identifiers are as listed.

| Identifier | Description |
| --- | --- |
| IRP_MJ_CREATE | Create IRP. In this instance, a create request could be used for either creating a new instance of a filter, or for creating some object such as a pin under a filter or a clock under a pin. This assumes that the first element in the driver object's extent contains a KSDEVICE_HEADER structure that is used to find the type of object to create, based on the name passed. If a parent file object is specified, then that object's KSDISPATCH_TABLE.ChildCreateHandlerTable in the **FsContext** is looked at to determine what handler to use for the create, or use the device object's table. |
| IRP_MJ_CLOSE | Close IRP. |
| IRP_MJ_DEVICE_CONTROL | Device control IRP. |
| IRP_MJ_READ | Read IRP. |
| IRP_MJ_WRITE | Write IRP. |
| IRP_MJ_FLUSH_BUFFERS | Flush IRP. |
| IRP_MJ_QUERY_SECURITY | Query security information. |
| IRP_MJ_SET_SECURITY | Set security information. |
| KSDISPATCH_FASTIO | This flag may be added to the MajorFunction identifier in order to specify that the entry refers to the fast I/O dispatch table, rather than the typical major function entry. This is valid only with IRP_MJ_READ, IRP_MJ_WRITE or IRP_MJ_DEVICE_CONTROL. The driver is responsible for creating the DriverObject->FastIoDispatch table. As with normal dispatching, if a handler is set for the driver object, all file objects must handle that fast I/O, even if the entry just points to DispatchFastIoDeviceControlFailure or a similar function. |

## -returns

Returns STATUS_SUCCESS if the MajorFunction identifier is valid.

## -remarks

If a major function handler is set for a driver object, all file objects must handle that major function, even if the entry just points to **KsDispatchInvalidDeviceRequest**.

```cpp
KSDISPATCH_FASTIO
```

This flag may be used to specify that the fast I/O entry should be set rather than the IRP-based entry.
