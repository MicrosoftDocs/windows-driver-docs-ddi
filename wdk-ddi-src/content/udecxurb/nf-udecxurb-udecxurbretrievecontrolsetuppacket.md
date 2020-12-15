---
UID: NF:udecxurb.UdecxUrbRetrieveControlSetupPacket
title: UdecxUrbRetrieveControlSetupPacket function (udecxurb.h)
description: Retrieves a USB control setup packet from a specified framework request object.
old-location: buses\udecxurbretrievecontrolsetuppacket.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UdecxUrbRetrieveControlSetupPacket function"]
ms.keywords: UdecxUrbRetrieveControlSetupPacket, UdecxUrbRetrieveControlSetupPacket function [Buses], buses.udecxurbretrievecontrolsetuppacket, udecxurb/UdecxUrbRetrieveControlSetupPacket
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
targetos: Windows
req.typenames: 
f1_keywords:
 - UdecxUrbRetrieveControlSetupPacket
 - udecxurb/UdecxUrbRetrieveControlSetupPacket
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxUrbRetrieveControlSetupPacket
---

# UdecxUrbRetrieveControlSetupPacket function


## -description

Retrieves a USB control setup packet from  a specified framework request object.

## -parameters

### -param Request 

[in]
A handle to a framework request object that represents the request containing the setup packet.

### -param SetupPacket 

[out]
A <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure that receives a setup packet describing the USB control transfer.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

## -remarks

The client driver can inspect contents of the setup packet to determine the standard control request that is sent to the device.

To complete the request, the driver must call <a href="/windows-hardware/drivers/ddi/udecxurb/nf-udecxurb-udecxurbcompletewithntstatus">UdecxUrbCompleteWithNtStatus</a>.

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
