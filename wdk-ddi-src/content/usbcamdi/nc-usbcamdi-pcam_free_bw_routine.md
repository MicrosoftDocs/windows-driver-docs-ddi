---
UID: NC:usbcamdi.PCAM_FREE_BW_ROUTINE
title: PCAM_FREE_BW_ROUTINE (usbcamdi.h)
description: A camera minidriver's CamFreeBandwidth callback function selects an alternate setting within the USB video streaming interface that uses no bandwidth.
old-location: stream\camfreebandwidth.htm
tech.root: stream
ms.assetid: 360fd299-bb8a-4fbb-899d-0e5fbe228d80
ms.date: 04/23/2018
keywords: ["PCAM_FREE_BW_ROUTINE callback function"]
ms.keywords: CamFreeBandwidth, CamFreeBandwidth callback function [Streaming Media Devices], PCAM_FREE_BW_ROUTINE, PCAM_FREE_BW_ROUTINE callback, stream.camfreebandwidth, usbcamdi/CamFreeBandwidth, usbcmdpr_bf8779db-a06c-49b8-aa2f-e558a53bfa93.xml
f1_keywords:
 - "usbcamdi/CamFreeBandwidth"
 - "CamFreeBandwidth"
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
- CamFreeBandwidth
targetos: Windows
req.typenames: 
---

# PCAM_FREE_BW_ROUTINE callback function


## -description


<p class="CCE_Message">[CamFreeBandwidth is not supported and may be altered or unavailable in the future. Instead, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_free_bw_routine_ex">CamFreeBandwidthEx</a>.
]

A camera minidriver's <b>CamFreeBandwidth</b> callback function selects an alternate setting within the USB video streaming interface that uses no bandwidth.


## -parameters




### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.


### -param DeviceContext

Pointer to the camera minidriver's device context.


## -returns



<b>CamFreeBandwidth</b> returns STATUS_SUCCESS or an appropriate error code.




## -remarks



Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_usbcamd_device_data">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the camera minidriver's <b>CamFreeBandwidth</b> callback function after the isochronous video stream has stopped.

Typically, this function calls the <b>USBCAMD_SelectAlternateInterface</b> service to select the correct alternate interface and prepare for streaming video.

This function is required.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_free_bw_routine_ex">CamFreeBandwidthEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nf-usbcamdi-usbcamd_selectalternateinterface">USBCAMD_SelectAlternateInterface</a>
 

 

