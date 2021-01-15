---
UID: NC:usbcamdi.PCAM_NEW_FRAME_ROUTINE_EX
title: PCAM_NEW_FRAME_ROUTINE_EX (usbcamdi.h)
description: A camera minidriver's CamNewVideoFrameEx callback function initializes a new video frame context structure.
old-location: stream\camnewvideoframeex.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["PCAM_NEW_FRAME_ROUTINE_EX callback function"]
ms.keywords: CamNewVideoFrameEx, CamNewVideoFrameEx routine [Streaming Media Devices], PCAM_NEW_FRAME_ROUTINE_EX, stream.camnewvideoframeex, usbcamdi/CamNewVideoFrameEx, usbcmdpr_e7d56a12-73a6-4778-91be-24962683c475.xml
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
 - PCAM_NEW_FRAME_ROUTINE_EX
 - usbcamdi/PCAM_NEW_FRAME_ROUTINE_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbcamdi.h
api_name:
 - PCAM_NEW_FRAME_ROUTINE_EX
---

# PCAM_NEW_FRAME_ROUTINE_EX callback function


## -description

A camera minidriver's <b>CamNewVideoFrameEx</b> callback function initializes a new video frame context structure.

## -parameters

### -param DeviceContext

Specifies the minidriver device context.

### -param FrameContext

Specifies the frame context to be initialized.

### -param StreamNumber

Indicates the stream associated with this new frame.

### -param FrameLength

Pointer to the raw frame buffer length. The length is expressed in bytes. The camera minidriver may decrease this value if it does not require a buffer transfer on the USB bus of the specified size. The camera minidriver should not increase this value.

## -remarks

USBCAMD calls the camera minidriver's <b>CamNewVideoFrameEx</b> callback function at IRQL = DISPATCH_LEVEL.

The original USBCAMD does not call <b>CamNewVideoFrameEx</b>.

This function is optional.

