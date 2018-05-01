---
UID: NF:usbcamdi.USBCAMD_AdapterReceivePacket
title: USBCAMD_AdapterReceivePacket function
author: windows-driver-content
description: The USBCAMD_AdapterReceivePacket function allows USBCAMD to process an adapter-based stream request block (SRB).
old-location: stream\usbcamd_adapterreceivepacket.htm
old-project: stream
ms.assetid: 12a5ca64-7187-4a70-83ca-0ade6a8b1343
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: USBCAMD_AdapterReceivePacket, USBCAMD_AdapterReceivePacket function [Streaming Media Devices], stream.usbcamd_adapterreceivepacket, usbcamdi/USBCAMD_AdapterReceivePacket, usbcmdpr_ad9c24d0-76a2-43a4-9634-a70e9260d907.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: Usbcamd2.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	usbcamd2.lib
-	usbcamd2.dll
api_name:
-	USBCAMD_AdapterReceivePacket
product: Windows
targetos: Windows
req.typenames: 
---

# USBCAMD_AdapterReceivePacket function


## -description


The <b>USBCAMD_AdapterReceivePacket</b> function allows USBCAMD to process an adapter-based stream request block (SRB).


## -parameters




### -param Srb [in]

Pointer to the SRB passed to the camera minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554080">AdapterReceivePacket</a> callback function.


### -param DeviceData [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568585">USBCAMD_DEVICE_DATA</a> structure that contains entry points to the camera minidriver's callback functions.


### -param DeviceObject [in]

Pointer to the device's physical device object (PDO).


### -param NeedsCompletion [in]

Specifies if USBCAMD is to process and complete the SRB request. Specify <b>TRUE</b> if USBCAMD is to complete the SRB request Specify <b>FALSE</b> to make USBCAMD ignore the SRB request and return the device context pointer.


## -returns



<b>USBCAMD_AdapterReceivePacket</b> returns a pointer to the device-specific context for this instance of the camera.




## -remarks



Typically, this function is called by the camera minidriver from its <a href="https://msdn.microsoft.com/library/windows/hardware/ff554080">AdapterReceivePacket</a> routine. 

This function can also be used by the minidriver to retrieve the device context by setting the <i>NeedsCompletion</i> parameter to <b>FALSE</b>. In this case, the <i>DeviceData</i> and <i>DeviceObject</i> parameters are ignored.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554080">AdapterReceivePacket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568585">USBCAMD_DEVICE_DATA</a>
 

 

