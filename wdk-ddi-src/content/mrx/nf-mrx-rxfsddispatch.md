---
UID: NF:mrx.RxFsdDispatch
title: RxFsdDispatch function (mrx.h)
description: Learn more about the RxFsdDispatch function.
tech.root: ifsk
ms.date: 10/11/2023
keywords: ["RxFsdDispatch function"]
ms.keywords: RxFsdDispatch, RxFsdDispatch routine [Installable File System Drivers], ifsk.rxfsddispatch, mrx/RxFsdDispatch, rxref_23ec1489-9629-4aef-b0b0-d844364b67a7.xml
req.header: mrx.h
req.include-header: Mrx.h, Rxstruc.h, Struchdr.h
req.target-type: Desktop
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RxFsdDispatch
 - mrx/RxFsdDispatch
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mrx.h
api_name:
 - RxFsdDispatch
---

# RxFsdDispatch function

## -description

**RxFsdDispatch** implements the file system driver (FSD) dispatch for RDBSS to process an I/O request packet (IRP). A pointer to this routine is copied over the device driver dispatch table for the network mini-redirector driver by the **RxDriverEntry** routine when RDBSS is initialized.

## -parameters

### -param RxDeviceObject [in]

A pointer to the RDBSS device object for this network mini-redirector.

### -param Irp [in]

A pointer to the I/O request packet being processed.

## -returns

**RxFsdDispatch** returns one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_INVALID_DEVICE_REQUEST | A request was made on an invalid device object. For example, this error is returned if a file system object is passed as the **RxDeviceObject** parameter. This status value indicates failure. |
| STATUS_OBJECT_NAME_INVALID | An invalid request was made to create a named pipe or a mailslot (the **MajorFunction** member of the **Irp** was IRP_MJ_CREATE_MAILSLOT or IRP_MJ_CREATE_NAMED_PIPE). This status value indicates failure. |
| STATUS_PENDING | An asynchronous request was made and the status of the request is pending. |
| STATUS_SUCCESS | The **RxFsdDispatch** routine call was successful. |

## -remarks

**RxFsdDispatch** is called by RDBSS to process an I/O request packet (IRP). These IRPs are normally received by RDBSS in response to a user-mode application requesting operations on a file. It is also possible for another kernel driver to issue such an IRP.

A pointer to **RxFsdDispatch** routine is copied over the driver dispatch table for a network mini-redirector driver when the **RxDriverEntry** routine is called to initialize RDBSS.

Internally, RDBSS maintains two dispatch vectors:

* A common dispatch vector for most operations.

* A private dispatch vector for file device FCB operations.

If the IRP is an IRP_MJ_CREATE request, then **RxFsdDispatch** will use a common dispatch vector. If the IRP is for an operation on an FCB of a file object, **RxFsdDispatch** will check if a private dispatch vector should be used. Otherwise a common dispatch vector will be used to process the IRP.

**RxFsdDispatch** calls internal routines to process the standard IRPs most of which result in a call to one of the callback routines implemented by the network mini-redirector driver.

A few IRPs are treated as special and handled internally by RDBSS. For example, the IRP_MJ_SYSTEM_CONTROL is used internally if WMI is enabled. IRP_MJ_CREATE_MAILSLOT or IRP_MJ_CREATE_NAMED_PIPE requests are treated specially and rejected (a STATUS_OBJECT_NAME_INVALID error is returned).

## -see-also

[**RxDriverEntry**](../rxprocs/nf-rxprocs-rxdriverentry.md)
