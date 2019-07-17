---
UID: NC:usbcamdi.PCAM_FREE_BW_ROUTINE_EX
title: PCAM_FREE_BW_ROUTINE_EX (usbcamdi.h)
description: A camera minidriver's CamFreeBandwidthEx callback function selects an alternate setting within the USB video streaming interface that uses no bandwidth.
old-location: stream\camfreebandwidthex.htm
tech.root: stream
ms.assetid: ef6aa2bf-8b45-4048-ac21-b069e28b556f
ms.date: 04/23/2018
ms.keywords: CamFreeBandwidthEx, CamFreeBandwidthEx routine [Streaming Media Devices], PCAM_FREE_BW_ROUTINE_EX, stream.camfreebandwidthex, usbcamdi/CamFreeBandwidthEx, usbcmdpr_bf3efd8f-3320-469c-a358-85cf2d896caf.xml
ms.topic: callback
f1_keywords:
 - "usbcamdi/CamFreeBandwidthEx"
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
- CamFreeBandwidthEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCAM_FREE_BW_ROUTINE_EX callback function


## -description


A camera minidriver's <b>CamFreeBandwidthEx</b> callback function selects an alternate setting within the USB video streaming interface that uses no bandwidth.


## -parameters




### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.


### -param DeviceContext

Pointer to the camera minidriver's device context.


### -param STreamNumber








#### - StreamNumber

Indicates stream number.


## -returns



<b>CamFreeBandwidthEx</b> returns STATUS_SUCCESS or an appropriate error code.




## -remarks



USBCAMD calls the camera minidriver's <b>CamFreeBandwidthEx</b> callback function after the isochronous video stream has stopped.

Typically, this function calls the <b>USBCAMD_SelectAlternateInterface</b> service to select the correct alternate interface and prepare for streaming video.

The original USBCAMD does not call <b>CamFreeBandwidthEx</b>.

This function is required.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbcamdi/ns-usbcamdi-_usbcamd_device_data2">USBCAMD_DEVICE_DATA2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbcamdi/nf-usbcamdi-usbcamd_selectalternateinterface">USBCAMD_SelectAlternateInterface</a>
 

 

