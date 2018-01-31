---
UID: NC:usbcamdi.PCAM_FREE_BW_ROUTINE
title: PCAM_FREE_BW_ROUTINE
author: windows-driver-content
description: A camera minidriver's CamFreeBandwidth callback function selects an alternate setting within the USB video streaming interface that uses no bandwidth.
old-location: stream\camfreebandwidth.htm
old-project: stream
ms.assetid: 360fd299-bb8a-4fbb-899d-0e5fbe228d80
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.camfreebandwidth, CamFreeBandwidth callback function [Streaming Media Devices], CamFreeBandwidth, PCAM_FREE_BW_ROUTINE, PCAM_FREE_BW_ROUTINE, usbcamdi/CamFreeBandwidth, usbcmdpr_bf8779db-a06c-49b8-aa2f-e558a53bfa93.xml
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	usbcamdi.h
apiname:
-	CamFreeBandwidth
product: Windows
targetos: Windows
req.typenames: "*PUSB_BUS_INTERFACE_USBDI_V3, USB_BUS_INTERFACE_USBDI_V3"
req.product: Windows 10 or later.
---

# PCAM_FREE_BW_ROUTINE callback


## -description


<p class="CCE_Message">[CamFreeBandwidth is not supported and may be altered or unavailable in the future. Instead, use <a href="..\usbcamdi\nc-usbcamdi-pcam_free_bw_routine_ex.md">CamFreeBandwidthEx</a>.
]

A camera minidriver's <b>CamFreeBandwidth</b> callback function selects an alternate setting within the USB video streaming interface that uses no bandwidth.


## -prototype


````
NTSTATUS CamFreeBandwidth(
   PDEVICE_OBJECT BusDeviceObject,
   PVOID          DeviceContext
);
````


## -parameters




#### - BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.


#### - DeviceContext

Pointer to the camera minidriver's device context.


## -returns


<b>CamFreeBandwidth</b> returns STATUS_SUCCESS or an appropriate error code.



## -remarks


Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the camera minidriver's <b>CamFreeBandwidth</b> callback function after the isochronous video stream has stopped.

Typically, this function calls the <b>USBCAMD_SelectAlternateInterface</b> service to select the correct alternate interface and prepare for streaming video.

This function is required.



## -see-also

<a href="..\usbcamdi\nc-usbcamdi-pcam_free_bw_routine_ex.md">CamFreeBandwidthEx</a>

<a href="..\usbcamdi\nf-usbcamdi-usbcamd_selectalternateinterface.md">USBCAMD_SelectAlternateInterface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PCAM_FREE_BW_ROUTINE callback function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

