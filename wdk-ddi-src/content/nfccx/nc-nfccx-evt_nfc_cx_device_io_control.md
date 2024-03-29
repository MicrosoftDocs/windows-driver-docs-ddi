---
UID: NC:nfccx.EVT_NFC_CX_DEVICE_IO_CONTROL
title: EVT_NFC_CX_DEVICE_IO_CONTROL (nfccx.h)
description: Called by the NFC CX to send an unhandled IOCTL to the client driver.
old-location: nfpdrivers\evtnfccxdeviceiocontrol_.htm
tech.root: nfpdrivers
ms.date: 02/15/2018
keywords: ["EVT_NFC_CX_DEVICE_IO_CONTROL callback function"]
ms.keywords: EVT_NFC_CX_DEVICE_IO_CONTROL, EVT_NFC_CX_DEVICE_IO_CONTROL callback, EvtNfcCxDeviceIoControl, EvtNfcCxDeviceIoControl callback function [Near-Field Proximity Drivers], nfccx/EvtNfcCxDeviceIoControl, nfpdrivers.evtnfccxdeviceiocontrol_
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
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
req.irql: Requires same
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_NFC_CX_DEVICE_IO_CONTROL
 - nfccx/EVT_NFC_CX_DEVICE_IO_CONTROL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - nfccx.h
api_name:
 - EVT_NFC_CX_DEVICE_IO_CONTROL
---

# EVT_NFC_CX_DEVICE_IO_CONTROL callback function


## -description

Called by the NFC CX to send an unhandled IOCTL to the client driver.

## -parameters

### -param Device [in]


A handle to a framework device object.

### -param Request [in]


A handle to a framework request object.

### -param OutputBufferLength [in]


The length, in bytes, of the request's output buffer, if an output buffer is available.

### -param InputBufferLength [in]


The length, in bytes, of the request's input buffer, if an input buffer is available.

### -param IoControlCode [in]


The driver-defined or system-defined I/O control code (<a href="/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_ioctl_routine">IOCTL</a>) that is associated with the request.

## -remarks

The client can complete the request either synchronously or asynchronously. The NFC CX will complete the request if a status code other than STATUS_PENDING is returned by the client. To prevent request double completion, the client should not complete the WDFREQUEST (that is, call <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> or <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcompletewithinformation">WdfRequestCompleteWithInformation</a>) if it returns STATUS_SUCCESS or a failure status code.

## -see-also

<a href="/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="/windows-hardware/drivers/nfc/">Near field communication (NFC) design guide</a>

