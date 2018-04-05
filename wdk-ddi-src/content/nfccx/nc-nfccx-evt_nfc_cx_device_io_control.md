---
UID: NC:nfccx.EVT_NFC_CX_DEVICE_IO_CONTROL
title: EVT_NFC_CX_DEVICE_IO_CONTROL
author: windows-driver-content
description: Called by the NFC CX to send an unhandled IOCTL to the client driver.
old-location: nfpdrivers\evtnfccxdeviceiocontrol_.htm
old-project: nfpdrivers
ms.assetid: 45512F88-D4B8-4488-99EB-B47EE7443425
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: EVT_NFC_CX_DEVICE_IO_CONTROL, EvtNfcCxDeviceIoControl, EvtNfcCxDeviceIoControl callback function [Near-Field Proximity Drivers], nfccx/EvtNfcCxDeviceIoControl, nfpdrivers.evtnfccxdeviceiocontrol_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	nfccx.h
api_name:
-	EvtNfcCxDeviceIoControl
product:
- Windows
targetos: Windows
req.typenames: NET_PNP_EVENT, *PNET_PNP_EVENT
---

# EVT_NFC_CX_DEVICE_IO_CONTROL callback


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

The driver-defined or system-defined I/O control code (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551084">IOCTL</a>) that is associated with the request.


## -returns



This callback function does not return a value.




## -remarks



The client can complete the request either synchronously or asynchronously. The NFC CX will complete the request if a status code other than STATUS_PENDING is returned by the client. To prevent request double completion, the client should not complete the WDFREQUEST (that is, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549948">WdfRequestCompleteWithInformation</a>) if it returns STATUS_SUCCESS or a failure status code.




## -see-also




<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>
 

 

