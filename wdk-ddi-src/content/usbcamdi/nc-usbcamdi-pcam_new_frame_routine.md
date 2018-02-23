---
UID: NC:usbcamdi.PCAM_NEW_FRAME_ROUTINE
title: PCAM_NEW_FRAME_ROUTINE
author: windows-driver-content
description: A camera minidriver's CamNewVideoFrame callback function initializes a new video frame context structure.
old-location: stream\camnewvideoframe.htm
old-project: stream
ms.assetid: b647cc94-e5eb-494f-b103-22aa30da8946
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: stream.camnewvideoframe, CamNewVideoFrame, CamNewVideoFrame callback function [Streaming Media Devices], CamNewVideoFrame, PCAM_NEW_FRAME_ROUTINE, PCAM_NEW_FRAME_ROUTINE, usbcamdi/CamNewVideoFrame, usbcmdpr_5f488227-2c1a-497e-975a-dc2b388f8489.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	usbcamdi.h
apiname:
-	CamNewVideoFrame
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# PCAM_NEW_FRAME_ROUTINE callback


## -description


<p class="CCE_Message">[CamNewVideoFrame is not supported and may be altered or unavailable in the future. Instead, use <a href="..\usbcamdi\nc-usbcamdi-pcam_new_frame_routine_ex.md">CamNewVideoFrameEx</a>.
]

A camera minidriver's <b>CamNewVideoFrame</b> callback function initializes a new video frame context structure.


## -prototype


````
VOID CamNewVideoFrame(
   PVOID DeviceContext,
   PVOID FrameContext
);
````


## -parameters




### -param DeviceContext

Pointer to the camera minidriver's device context.


### -param FrameContext

Pointer to the camera minidriver's frame context.


## -returns



<b>CamNewVideoFrame</b> does not return a value.




## -remarks



Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the camera minidriver's <b>CamNewVideoFrame</b> callback function at IRQL = DISPATCH_LEVEL.

This function is optional.




## -see-also

<a href="..\usbcamdi\nc-usbcamdi-pcam_new_frame_routine_ex.md">CamNewVideoFrameEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PCAM_NEW_FRAME_ROUTINE callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

