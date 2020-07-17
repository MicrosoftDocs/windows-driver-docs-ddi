---
UID: NC:usbcamdi.PCAM_PROCESS_PACKET_ROUTINE
title: PCAM_PROCESS_PACKET_ROUTINE (usbcamdi.h)
description: A camera minidriver's CamProcessUSBPacket callback function processes a USB packet.
old-location: stream\camprocessusbpacket.htm
tech.root: stream
ms.assetid: 2b83d1b1-82f6-455b-b22a-ae9433dd9f27
ms.date: 04/23/2018
keywords: ["PCAM_PROCESS_PACKET_ROUTINE callback function"]
ms.keywords: CamProcessUSBPacket, CamProcessUSBPacket callback function [Streaming Media Devices], PCAM_PROCESS_PACKET_ROUTINE, PCAM_PROCESS_PACKET_ROUTINE callback, stream.camprocessusbpacket, usbcamdi/CamProcessUSBPacket, usbcmdpr_7eeca66e-b106-4cb0-b0c3-d7d07d82d841.xml
f1_keywords:
 - "usbcamdi/CamProcessUSBPacket"
 - "CamProcessUSBPacket"
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
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- usbcamdi.h
api_name:
- CamProcessUSBPacket
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCAM_PROCESS_PACKET_ROUTINE callback function


## -description


<p class="CCE_Message">[CamProcessUSBPacket is not supported and may be altered or unavailable in the future. Instead, use CamProcessUSBPacketEx.
]

A camera minidriver's <b>CamProcessUSBPacket</b> callback function processes a USB packet.


## -parameters




### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.


### -param DeviceContext

Pointer to the camera minidriver's device context.


### -param CurrentFrameContext

Pointer to the minidriver's frame context.


### -param SyncPacket

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_iso_packet_descriptor">USBD_ISO_PACKET_DESCRIPTOR</a> structure from the sync pipe. This value is <b>NULL</b> if the interface has only one pipe.


### -param SyncBuffer

Pointer to the data for the <i>SyncPacket.</i>


### -param DataPacket

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_iso_packet_descriptor">USBD_ISO_PACKET_DESCRIPTOR</a> structure from the data pipe.


### -param DataBuffer

Pointer to <i>DataPacket.</i>


### -param FrameComplete

Pointer to a BOOLEAN value that the camera minidriver sets to indicate whether this is the first data packet for a new video frame. Set to <b>TRUE</b> if this is the first data packet for a new video frame.


### -param NextFrameIsStill

Pointer to a BOOLEAN value that the camera minidriver sets to indicate whether the next frame is a still frame or not. This value should be set to <b>FALSE</b> if the video stream is providing a live image or <b>TRUE</b> if the next frame is a still image or an image capture stream.


## -returns



This callback function returns a ULONG that indicates the number of bytes that should be copied into the buffer (<i>RawFrameBuffer</i> or <i>FrameBuffer)</i>.




## -remarks



Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_usbcamd_device_data">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

The minidriver should complete this function as quickly as possible. Image processing should be deferred to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_process_raw_frame_routine">CamProcessRawVideoFrame</a> function.

This function is optional.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_process_raw_frame_routine">CamProcessRawVideoFrame</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_process_packet_routine_ex">CamProcessUSBPacketEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_iso_packet_descriptor">USBD_ISO_PACKET_DESCRIPTOR</a>
 

 

