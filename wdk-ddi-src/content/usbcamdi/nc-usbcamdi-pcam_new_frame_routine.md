---
UID: NC:usbcamdi.PCAM_NEW_FRAME_ROUTINE
title: PCAM_NEW_FRAME_ROUTINE (usbcamdi.h)
description: A camera minidriver's CamNewVideoFrame callback function initializes a new video frame context structure.
old-location: stream\camnewvideoframe.htm
tech.root: stream
ms.assetid: b647cc94-e5eb-494f-b103-22aa30da8946
ms.date: 04/23/2018
keywords: ["PCAM_NEW_FRAME_ROUTINE callback function"]
ms.keywords: CamNewVideoFrame, CamNewVideoFrame callback function [Streaming Media Devices], PCAM_NEW_FRAME_ROUTINE, PCAM_NEW_FRAME_ROUTINE callback, stream.camnewvideoframe, usbcamdi/CamNewVideoFrame, usbcmdpr_5f488227-2c1a-497e-975a-dc2b388f8489.xml
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
req.irql: DISPATCH_LEVEL (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - PCAM_NEW_FRAME_ROUTINE
 - usbcamdi/PCAM_NEW_FRAME_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbcamdi.h
api_name:
 - CamNewVideoFrame
---

# PCAM_NEW_FRAME_ROUTINE callback function


## -description

<p class="CCE_Message">[CamNewVideoFrame is not supported and may be altered or unavailable in the future. Instead, use <a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_new_frame_routine_ex">CamNewVideoFrameEx</a>.
]

A camera minidriver's <b>CamNewVideoFrame</b> callback function initializes a new video frame context structure.

## -parameters

### -param DeviceContext

Pointer to the camera minidriver's device context.

### -param FrameContext

Pointer to the camera minidriver's frame context.

## -remarks

Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_usbcamd_device_data">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the camera minidriver's <b>CamNewVideoFrame</b> callback function at IRQL = DISPATCH_LEVEL.

This function is optional.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_new_frame_routine_ex">CamNewVideoFrameEx</a>