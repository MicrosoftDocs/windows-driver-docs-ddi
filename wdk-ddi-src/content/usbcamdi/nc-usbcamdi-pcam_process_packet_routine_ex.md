---
UID: NC:usbcamdi.PCAM_PROCESS_PACKET_ROUTINE_EX
title: PCAM_PROCESS_PACKET_ROUTINE_EX (usbcamdi.h)
description: A camera minidriver's CamProcessUSBPacketEx callback function processes a USB packet.
tech.root: stream
ms.date: 03/08/2023
keywords: ["PCAM_PROCESS_PACKET_ROUTINE_EX callback function"]
ms.keywords: CamProcessUSBPacketEx, CamProcessUSBPacketEx routine [Streaming Media Devices], PCAM_PROCESS_PACKET_ROUTINE_EX, stream.camprocessusbpacketex, usbcamdi/CamProcessUSBPacketEx, usbcmdpr_bd37e77c-386b-4b94-ad7c-8b1c5c26799a.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PCAM_PROCESS_PACKET_ROUTINE_EX
 - usbcamdi/PCAM_PROCESS_PACKET_ROUTINE_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbcamdi.h
api_name:
 - PCAM_PROCESS_PACKET_ROUTINE_EX
---

## -description

A camera minidriver's **CamProcessUSBPacketEx** callback function processes a USB packet.

## -parameters

### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.

### -param DeviceContext

Pointer to the camera minidriver's device context.

### -param CurrentFrameContext

Pointer to the camera minidriver's frame context.

### -param SyncPacket

Pointer to a [**USBD_ISO_PACKET_DESCRIPTOR**](../usb/ns-usb-_usbd_iso_packet_descriptor.md) structure from the sync pipe. This value is **NULL** if the interface has only one pipe.

### -param SyncBuffer

Pointer to the data for the *SyncPacket*.

### -param DataPacket

Specifies the isochronous packet descriptor from data pipe.

### -param DataBuffer

Pointer to *DataPacket.*

### -param FrameComplete

Pointer to a BOOLEAN value that the camera minidriver sets to indicate whether this is the first data packet for a new video frame.

### -param PacketFlag

Pointer to a value that the minidriver sets to indicate the contents of the current frame. It should be set to one of the following values:

| Flag | Meaning |
|---|---|
| USBCAMD_PROCESSPACKETEX_DropFrame | The current frame is unsalvageable. The read IRP should be recycled. |
| USBCAMD_PROCESSPACKETEX_NextFrameIsStill | The frame is a still image. |
| USBCAMD_PROCESSPACKETEX_CurrentFrameIsStill | The current frame is for the still pin. |

### -param ValidDataOffset

Pointer to a ULONG value that indicates an offset from the beginning of the packet. USBCAMD should start the copy from this offset. This eliminates the extra buffer copy in the case of an in-band signal. If the camera is not using in-band signaling, *ValidDataOffset* should be set to zero.

## -returns

This function returns the number of bytes that should be copied.

## -remarks

The minidriver should complete its **CamProcessUSBPacketEx** function as quickly as possible. Image processing should be deferred to the [CamProcessRawVideoFrameEx](./nc-usbcamdi-pcam_process_raw_frame_routine_ex.md) function.

This callback function is used with isochronous pipes only (video or still streaming).

The original USBCAMD does not call **CamProcessUSBPacketEx**.

This function is optional.

## -see-also

[CamProcessRawVideoFrameEx](./nc-usbcamdi-pcam_process_raw_frame_routine_ex.md)

[**USBD_ISO_PACKET_DESCRIPTOR**](../usb/ns-usb-_usbd_iso_packet_descriptor.md)