---
UID: NF:udecxurb.UdecxUrbRetrieveControlSetupPacket
title: UdecxUrbRetrieveControlSetupPacket function
author: windows-driver-content
description: Retrieves a USB control setup packet from a specified framework request object.
old-location: buses\udecxurbretrievecontrolsetuppacket.htm
old-project: UsbRef
ms.assetid: 09D9AB68-12DB-442F-897B-6C6BD8B5F030
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , C, P, R, S, U, UdecxUrbRetrieveControlSetupPacket, UdecxUrbRetrieveControlSetupPacket function [Buses], a, b, buses.udecxurbretrievecontrolsetuppacket, c, d, e, i, k, l, n, o, p, r, t, u, udecxurb/UdecxUrbRetrieveControlSetupPacket, v, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: udecxurb.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Udecxstub.lib
-	Udecxstub.dll
apiname:
-	UdecxUrbRetrieveControlSetupPacket
product: Windows
targetos: Windows
req.typenames: USB_DEVICE_PORT_PATH, *PUSB_DEVICE_PORT_PATH
req.product: Windows 10 or later.
---

# UdecxUrbRetrieveControlSetupPacket function


## -description


Retrieves a USB control setup packet from  a specified framework request object.  


## -syntax


````
FORCEINLINE NTSTATUS UdecxUrbRetrieveControlSetupPacket(
  _In_  WDFREQUEST                    Request,
  _Out_ PWDF_USB_CONTROL_SETUP_PACKET SetupPacket
);
````


## -parameters




### -param Request [in]

A handle to a framework request object that represents the request containing the setup packet.


### -param SetupPacket [out]

A <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure that receives a setup packet describing the USB control transfer.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -remarks



The client driver can inspect contents of the setup packet to determine the standard control request that is sent to the device.

To complete the request, the driver must call <a href="..\udecxurb\nf-udecxurb-udecxurbcompletewithntstatus.md">UdecxUrbCompleteWithNtStatus</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UdecxUrbRetrieveControlSetupPacket function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

