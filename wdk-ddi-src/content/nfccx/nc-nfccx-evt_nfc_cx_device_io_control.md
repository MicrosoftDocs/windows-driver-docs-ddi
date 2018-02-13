---
UID: NC:nfccx.EVT_NFC_CX_DEVICE_IO_CONTROL
title: EVT_NFC_CX_DEVICE_IO_CONTROL
author: windows-driver-content
description: Called by the NFC CX to send an unhandled IOCTL to the client driver.
old-location: nfpdrivers\evtnfccxdeviceiocontrol_.htm
old-project: nfpdrivers
ms.assetid: 45512F88-D4B8-4488-99EB-B47EE7443425
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: nfpdrivers.evtnfccxdeviceiocontrol_, EvtNfcCxDeviceIoControl callback function [Near-Field Proximity Drivers], EvtNfcCxDeviceIoControl, EVT_NFC_CX_DEVICE_IO_CONTROL, EVT_NFC_CX_DEVICE_IO_CONTROL, nfccx/EvtNfcCxDeviceIoControl
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	nfccx.h
apiname:
-	EvtNfcCxDeviceIoControl
product: Windows
targetos: Windows
req.typenames: NPI_REGISTRATION_INSTANCE
---

# EVT_NFC_CX_DEVICE_IO_CONTROL callback


## -description


Called by the NFC CX to send an unhandled IOCTL to the client driver.


## -prototype


````
EVT_NFC_CX_DEVICE_IO_CONTROL EvtNfcCxDeviceIoControl;

void EvtNfcCxDeviceIoControl(
  _In_ WDFDEVICE  Device,
  _In_ WDFREQUEST Request,
  _In_ size_t     OutputBufferLength,
  _In_ size_t     InputBufferLength,
  _In_ ULONG      IoControlCode
)
{ ... }
````


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



The client can complete the request either synchronously or asynchronously. The NFC CX will complete the request if a status code other than STATUS_PENDING is returned by the client. To prevent request double completion, the client should not complete the WDFREQUEST (that is, call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a>) if it returns STATUS_SUCCESS or a failure status code.




## -see-also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20EVT_NFC_CX_DEVICE_IO_CONTROL callback function%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

