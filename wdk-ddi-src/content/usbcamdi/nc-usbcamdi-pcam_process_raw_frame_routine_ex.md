---
UID: NC:usbcamdi.PCAM_PROCESS_RAW_FRAME_ROUTINE_EX
title: PCAM_PROCESS_RAW_FRAME_ROUTINE_EX
author: windows-driver-content
description: A camera minidriver's CamProcessRawVideoFrameEx callback function decodes a raw video frame.
old-location: stream\camprocessrawvideoframeex.htm
old-project: stream
ms.assetid: 07b0d1ea-c099-474e-8dc8-cddec44836e2
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: stream.camprocessrawvideoframeex, CamProcessRawVideoFrameEx, CamProcessRawVideoFrameEx routine [Streaming Media Devices], CamProcessRawVideoFrameEx, PCAM_PROCESS_RAW_FRAME_ROUTINE_EX, PCAM_PROCESS_RAW_FRAME_ROUTINE_EX, usbcamdi/CamProcessRawVideoFrameEx, usbcmdpr_7ca6e89a-089c-4cf0-83e3-6324357a8566.xml
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	usbcamdi.h
apiname:
-	CamProcessRawVideoFrameEx
product: Windows
targetos: Windows
req.typenames: "*PUSB_BUS_INTERFACE_USBDI_V3, USB_BUS_INTERFACE_USBDI_V3"
req.product: Windows 10 or later.
---

# PCAM_PROCESS_RAW_FRAME_ROUTINE_EX callback


## -description


A camera minidriver's <b>CamProcessRawVideoFrameEx</b> callback function decodes a raw video frame.


## -prototype


````
PCAM_PROCESS_RAW_FRAME_ROUTINE_EX CamProcessRawVideoFrameEx;

NTSTATUS CamProcessRawVideoFrameEx(
   PDEVICE_OBJECT BusDeviceObject,
   PVOID          DeviceContext,
   PVOID          FrameContext,
   PVOID          FrameBuffer,
   ULONG          FrameLength,
   PVOID          RawFrameBuffer,
   ULONG          RawFrameLength,
   ULONG          NumberOfPackets,
   PULONG         BytesReturned,
   ULONG          ActualRawFrameLength,
   ULONG          StreamNumber
)
{ ... }
````


## -parameters




### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.


### -param DeviceContext

Pointer to the camera minidriver's device context.


### -param FrameContext

Pointer to the minidriver's frame context.


### -param FrameBuffer

Pointer to the buffer that receives the final processed video frame. See the Remarks section for more information about how USBCAMD uses this parameter.


### -param FrameLength

Specifies the length of the frame buffer (from the original read request) in bytes.


### -param RawFrameBuffer

Pointer to the buffer containing the received USB packets. See the Remarks section for more information about how USBCAMD uses this parameter.


### -param RawFrameLength

Specifies the length of <i>RawFrameBuffer</i> in bytes.


### -param NumberOfPackets

Specifies the number of USB packets received into <i>RawFrameBuffer</i>.


### -param BytesReturned

Pointer to the number of bytes transferred. The minidriver must set this to zero if it encounters any errors during processing, as described in <a href="https://msdn.microsoft.com/a66f4191-53ce-4ca2-aae7-8fb24a1a9a16">Data Flow Using Isochronous Pipes</a>. See the Remarks section for more information about how USBCAMD uses this parameter.


### -param ActualRawFrameLength

Contains the length of the actual buffer received from the camera. This value is specified in bytes.


### -param StreamNumber

Indicates the stream number with which this frame is associated with.


## -returns



<b>CamProcessRawVideoFrameEx</b> returns STATUS_SUCCESS or an appropriate error code.




## -remarks



Before USBCAMD calls the minidriver's <b>CamProcessRawVideoFrameEx</b> callback, it sets the first DWORD in the buffer pointed to by the <i>FrameBuffer</i> parameter to the value <i>0xdeadbeef.</i> After calling the minidriver's <b>CamProcessRawVideoFrameEx</b> callback USBCAMD checks the first DWORD in the buffer pointed to by the <i>FrameBuffer</i> parameter for the value <i>0xdeadbeef</i> to determine if <b>CamProcessRawVideoFrameEx</b> successfully copied the video frame from the buffer pointed to by the <i>RawFrameBuffer</i> parameter into the buffer pointed to by the <i>FrameBuffer</i> parameter.

This function is not called if either one of the following bits are set in the <i>CamControlFlag</i> argument passed to the <a href="..\usbcamdi\nf-usbcamdi-usbcamd_initializenewinterface.md">USBCAMD_InitializeNewInterface</a> function:

USBCAMD_CamControlFlag_NoVideoRawProcessing

USBCAMD_CamControlFlag_NoStillRawProcessing

USBCAMD clears the stream header options flag before passing the raw frame to the minidriver. The default flag is key frames only. The camera minidriver should set the stream header option flags appropriately if it needs to indicate anything other than key frames.

The original USBCAMD does not call <b>CamProcessRawVideoFrameEx</b>.

This function is optional.



