---
UID: NF:usbcamdi.USBCAMD_DriverEntry
title: USBCAMD_DriverEntry function
author: windows-driver-content
description: The USBCAMD_DriverEntry function registers the minidriver with USBCAMD, effectively binding USBCAMD and the minidriver together.
old-location: stream\usbcamd_driverentry.htm
tech.root: stream
ms.assetid: ac77b121-2495-4739-8c8f-96d6c48e4dc6
ms.date: 4/23/2018
ms.keywords: USBCAMD_DriverEntry, USBCAMD_DriverEntry function [Streaming Media Devices], stream.usbcamd_driverentry, usbcamdi/USBCAMD_DriverEntry, usbcmdpr_3aeb66f4-1729-400c-af6d-6e1290c9fe3b.xml
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
-	USBCAMD_DriverEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBCAMD_DriverEntry function


## -description


The <b>USBCAMD_DriverEntry</b> function registers the minidriver with USBCAMD, effectively binding USBCAMD and the minidriver together.


## -parameters




### -param Context1 [in]

Pointer to the first argument that is passed to the camera minidriver's DriverEntry function. This is effectively a pointer to the driver object that is created by the system and passed to DriverEntry.


### -param Context2 [in]

Pointer to the second argument that is passed to the camera minidriver's DriverEntry function. This is effectively a pointer to the registry path that describes the minidriver's registry key.


### -param DeviceContextSize [in]

Specifies the size, in bytes, required for the minidriver's device-specific context.


### -param FrameCOntextSize




### -param ReceivePacket [in]

Pointer to the minidriver-defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff554080">AdapterReceivePacket</a> function that handles adapter-based SRB requests.


#### - FrameContextSize [in]

Specifies the size, in bytes, required for the minidriver's frame-specific context structure. Use <b>NULL</b> if not needed.


## -returns



<b>USBCAMD_DriverEntry </b>returns the status of the registration attempt. If a value other than STATUS_SUCCESS is returned, the minidriver is unloaded.




## -remarks



A camera minidriver must call <b>USBCAMD_DriverEntry</b> from the minidriver's <b>DriverEntry</b> routine. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558717">DriverEntry for Stream Class Minidrivers</a>


<i>FrameContextSize</i> is optional. A non-<b>NULL</b> value should be provided only with calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff557617">CamNewVideoFrame</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff557623">CamProcessRawVideoFrame</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554080">AdapterReceivePacket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557617">CamNewVideoFrame</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557623">CamProcessRawVideoFrame</a>
 

 

