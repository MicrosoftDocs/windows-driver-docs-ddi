---
UID: NF:udecxwdfdevice.UdecxWdfDeviceTryHandleUserIoctl
title: UdecxWdfDeviceTryHandleUserIoctl function (udecxwdfdevice.h)
description: Attempts to handle an IOCTL request sent by a user-mode software.
old-location: buses\udecxwdfdevicetryhandleuserioctl.htm
tech.root: usbref
ms.assetid: CC199F5C-BF05-4F1F-BEE4-8693F9156D8A
ms.date: 05/07/2018
ms.keywords: UdecxWdfDeviceTryHandleUserIoctl, UdecxWdfDeviceTryHandleUserIoctl function [Buses], buses.udecxwdfdevicetryhandleuserioctl, udecxwdfdevice/UdecxWdfDeviceTryHandleUserIoctl
ms.topic: function
req.header: udecxwdfdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Udecxstub.lib
-	Udecxstub.dll
api_name:
-	UdecxWdfDeviceTryHandleUserIoctl
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxWdfDeviceTryHandleUserIoctl function


## -description


Attempts to handle an IOCTL request sent by a user-mode software. 


## -parameters




### -param UdecxWdfDevice

<p>A handle to a framework device object that represents the controller. The client driver initialized this object in the previous call to <a href="https://msdn.microsoft.com/library/Mt627990(v=VS.85).aspx"><b>UdecxWdfDeviceAddUsbDeviceEmulation</b></a>.</p>


### -param Request [in]

A handle to a framework request object that represents the IOCTL request. 


## -returns



TRUE indicates that USB device emulation  class extension (UdeCx) recognized and completed the request (with success or failure). In this case, the client driver must
    not complete the request. FALSE otherwise; the driver must complete the request.




## -remarks



The UDE client driver presents itself to user-mode software as a host controller driver. The client driver registers and exposes the GUID_DEVINTERFACE_USB_HOST_CONTROLLER device interface GUID. User-mode software  can open a handle to the device by specifying that GUID. By using that handle, the software can send IOCTL requests. 

<div class="alert"><b>Note</b>  Note that other interface's IOCTL codes may overlap with the USB host controller interface. If
    such I/O reaches this function the IOCTL will not be handled correctly.</div>
<div> </div>
 The client driver does not need to process the received IOCTL. It can send the request to the class extension by calling <b>UdecxWdfDeviceTryHandleUserIoctl</b>. If the class extension recognizes the request as a standard request, it completes it. Otherwise, the call fails and the client driver is then expected to complete the request. For a list of IOCTLs that must be handled, see <a href="https://docs.microsoft.com/windows/iot-core/learn-about-hardware/hardwarecompatlist">USB IOCTLs for applications and services</a>.

<ul>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537236">IOCTL_GET_HCD_DRIVERKEY_NAME</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537326">IOCTL_USB_GET_ROOT_HUB_NAME</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537344">IOCTL_USB_USER_REQUEST</a>
</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

