---
UID: NC:usbcamdi.PADAPTER_RECEIVE_PACKET_ROUTINE
title: PADAPTER_RECEIVE_PACKET_ROUTINE (usbcamdi.h)
description: A camera minidriver's AdapterReceivePacket callback function processes adapter-based stream request blocks (SRBs) passed to it by the stream class driver.
old-location: stream\adapterreceivepacket.htm
tech.root: stream
ms.assetid: 8ee658bf-2243-4b1f-b4d6-5d9b6388e972
ms.date: 04/23/2018
ms.keywords: AdapterReceivePacket, AdapterReceivePacket callback function [Streaming Media Devices], PADAPTER_RECEIVE_PACKET_ROUTINE, PADAPTER_RECEIVE_PACKET_ROUTINE callback, stream.adapterreceivepacket, usbcamdi/AdapterReceivePacket, usbcmdpr_4f4422ba-64f3-4eee-8450-4a3b5715b910.xml
ms.topic: callback
f1_keywords:
 - "usbcamdi/AdapterReceivePacket"
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- usbcamdi.h
api_name:
- AdapterReceivePacket
product:
- Windows
targetos: Windows
req.typenames: 
---

# PADAPTER_RECEIVE_PACKET_ROUTINE callback function


## -description


A camera minidriver's <i>AdapterReceivePacket</i> callback function processes adapter-based stream request blocks (SRBs) passed to it by the stream class driver.


## -parameters




### -param Srb [in]

Specifies the SRB to be processed by the camera minidriver.


## -returns



<i>AdapterReceivePacket</i> does not return a value.




## -remarks



A camera's minidriver provides USBCAMD with the address of its <i>AdapterReceivePacket</i> function that processes SRBs in its call to the <b>USBCAMD_DriverEntry</b> service.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbcamdi/nf-usbcamdi-usbcamd_driverentry">USBCAMD_DriverEntry</a>
 

 

