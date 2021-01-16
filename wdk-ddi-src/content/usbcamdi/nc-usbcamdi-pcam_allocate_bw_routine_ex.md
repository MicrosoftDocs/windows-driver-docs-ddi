---
UID: NC:usbcamdi.PCAM_ALLOCATE_BW_ROUTINE_EX
title: PCAM_ALLOCATE_BW_ROUTINE_EX (usbcamdi.h)
description: A camera minidriver's CamAllocateBandwidthEx callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.
old-location: stream\camallocatebandwidthex.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["PCAM_ALLOCATE_BW_ROUTINE_EX callback function"]
ms.keywords: CamAllocateBandwidthEx, CamAllocateBandwidthEx routine [Streaming Media Devices], PCAM_ALLOCATE_BW_ROUTINE_EX, stream.camallocatebandwidthex, usbcamdi/CamAllocateBandwidthEx, usbcmdpr_dd4a1139-55b9-4342-9eeb-69e902497fa2.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PCAM_ALLOCATE_BW_ROUTINE_EX
 - usbcamdi/PCAM_ALLOCATE_BW_ROUTINE_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbcamdi.h
api_name:
 - PCAM_ALLOCATE_BW_ROUTINE_EX
---

# PCAM_ALLOCATE_BW_ROUTINE_EX callback function


## -description

A camera minidriver's <b>CamAllocateBandwidthEx</b> callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.

## -parameters

### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.

### -param DeviceContext

Pointer to the camera minidriver's device context.

### -param RawFrameLength

Specifies the size, in bytes, of the raw frame data from the packet stream.

### -param Format

Pointer to a <a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_dataformat_videoinfoheader">KS_DATAFORMAT_VIDEOINFOHEADER</a> structure associated with this stream.

### -param StreamNumber

Specifies the stream number.

## -returns

<b>CamAllocateBandwidthEx</b> returns STATUS_SUCCESS or an appropriate error code.

## -remarks

USBCAMD calls the camera minidriver's <b>CamAllocateBandwidthEx</b> callback function immediately before the isochronous video capture stream is started. It is called in connection with a <b>Run</b> command.

Typically, this function calls the <b>USBCAMD_SelectAlternateInterface</b> service to select the correct alternate interface and prepare for streaming video.

The original USBCAMD does not call <b>CamAllocateBandwidthEx</b>.

This function is required.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_dataformat_videoinfoheader">KS_DATAFORMAT_VIDEOINFOHEADER</a>



<a href="/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_usbcamd_device_data2">USBCAMD_DEVICE_DATA2</a>



<a href="/windows-hardware/drivers/ddi/usbcamdi/nf-usbcamdi-usbcamd_selectalternateinterface">USBCAMD_SelectAlternateInterface</a>

