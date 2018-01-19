---
UID: NC:usbcamdi.PCAM_ALLOCATE_BW_ROUTINE
title: PCAM_ALLOCATE_BW_ROUTINE
author: windows-driver-content
description: A camera minidriver's CamAllocateBandwidth callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.
old-location: stream\camallocatebandwidth.htm
old-project: stream
ms.assetid: 0dd01bf7-04a8-4d20-982a-1ec81076583f
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _USB_BUS_INTERFACE_USBDI_V3, USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
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
req.alt-api: CamAllocateBandwidth
req.alt-loc: usbcamdi.h
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
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# PCAM_ALLOCATE_BW_ROUTINE callback



## -description
<p class="CCE_Message">[CamAllocateBandwidth is not supported and may be altered or unavailable in the future. Instead, use <a href="..\usbcamdi\nc-usbcamdi-pcam_allocate_bw_routine_ex.md">CamAllocateBandwidthEx</a>.
]

A camera minidriver's <b>CamAllocateBandwidth</b> callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.



## -prototype

````
NTSTATUS CamAllocateBandwidth(
   PDEVICE_OBJECT BusDeviceObject,
   PVOID          DeviceContext,
   PULONG         RawFrameLength,
   PVOID          Format
);
````


## -parameters

### -param BusDeviceObject 

Pointer to the camera minidriver's device object created by the USB hub.


### -param DeviceContext 

Pointer to the camera minidriver's device context.


### -param RawFrameLength 

Specifies the size, of the raw frame data from the packet stream, in bytes.


### -param Format 

Pointer to a <a href="..\ksmedia\ns-ksmedia-tagks_dataformat_videoinfoheader.md">KS_DATAFORMAT_VIDEOINFOHEADER</a> structure that is associated with this stream.


## -returns
<b>CamAllocateBandwidth</b> returns STATUS_SUCCESS or an appropriate error code.


## -remarks
Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the camera minidriver's <b>CamAllocateBandwidth</b> callback function immediately before the isochronous video capture stream is started. It is called in connection with a <b>Run</b> command.

Typically, this function calls the <b>USBCAMD_SelectAlternateInterface</b> service to select the correct alternate interface and prepare for streaming video.

This function is required.


## -see-also
<dl>
<dt>
<a href="..\usbcamdi\nc-usbcamdi-pcam_allocate_bw_routine_ex.md">CamAllocateBandwidthEx</a>
</dt>
<dt>
<a href="..\usbcamdi\nf-usbcamdi-usbcamd_selectalternateinterface.md">USBCAMD_SelectAlternateInterface</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-tagks_dataformat_videoinfoheader.md">KS_DATAFORMAT_VIDEOINFOHEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PCAM_ALLOCATE_BW_ROUTINE callback function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

