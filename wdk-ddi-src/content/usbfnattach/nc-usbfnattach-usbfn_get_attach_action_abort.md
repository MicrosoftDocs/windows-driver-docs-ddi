---
UID: NC:usbfnattach.USBFN_GET_ATTACH_ACTION_ABORT
title: USBFN_GET_ATTACH_ACTION_ABORT (usbfnattach.h)
description: The filter driver's implementation to abort an attach-detect operation.
old-location: buses\usbfn_get_attach_action_abort.htm
tech.root: usbref
ms.assetid: 0A44551A-F379-442D-99E9-87231F5FB178
ms.date: 05/07/2018
keywords: ["USBFN_GET_ATTACH_ACTION_ABORT callback function"]
ms.keywords: USBFN_GET_ATTACH_ACTION_ABORT, USBFN_GET_ATTACH_ACTION_ABORT callback, UsbFnGetAttachActionAbort, UsbFnGetAttachActionAbort callback function [Buses], buses.usbfn_get_attach_action_abort, usbfnattach/UsbFnGetAttachActionAbort
req.header: usbfnattach.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - USBFN_GET_ATTACH_ACTION_ABORT
 - usbfnattach/USBFN_GET_ATTACH_ACTION_ABORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbfnattach.h
api_name:
 - USBFN_SET_DEVICE_STATE
---

# USBFN_GET_ATTACH_ACTION_ABORT callback function


## -description

The filter driver's implementation to abort an attach-detect operation.

## -parameters

### -param Context 

[in]
    A pointer to a driver-defined context.

## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## -remarks

To support attach and detatch detection, the USB lower filter driver must publish its support. During the publishing process, the driver also registers its implementation of this  callback function. For more information, see <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188012(v=vs.85)">USB filter driver for supporting proprietary chargers</a>.


#### Examples


```
NTSTATUS
UsbLowerFilter_GetAttachActionAbortOperation(
    __in PVOID Context
    )
{
    PPDCP_CONTEXT PdcpContext = NULL;

    PAGED_CODE();

    // Get our context
    PdcpContext = DeviceGetUsbLowerFilterContext((WDFDEVICE)Context);

    // Set our event
    (void) KeSetEvent(&PdcpContext->AbortAttachOperation, LOW_REALTIME_PRIORITY, FALSE);

    return STATUS_SUCCESS;
}

```


## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188012(v=vs.85)">USB filter driver for supporting proprietary chargers</a>

