---
UID: NC:usbcamdi.PCAM_FREE_BW_ROUTINE_EX
title: PCAM_FREE_BW_ROUTINE_EX
author: windows-driver-content
description: A camera minidriver's CamFreeBandwidthEx callback function selects an alternate setting within the USB video streaming interface that uses no bandwidth.
old-location: stream\camfreebandwidthex.htm
old-project: stream
ms.assetid: ef6aa2bf-8b45-4048-ac21-b069e28b556f
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: CamFreeBandwidthEx, CamFreeBandwidthEx routine [Streaming Media Devices], PCAM_FREE_BW_ROUTINE_EX, stream.camfreebandwidthex, usbcamdi/CamFreeBandwidthEx, usbcmdpr_bf3efd8f-3320-469c-a358-85cf2d896caf.xml
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
-	CamFreeBandwidthEx
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# PCAM_FREE_BW_ROUTINE_EX callback


## -description


A camera minidriver's <b>CamFreeBandwidthEx</b> callback function selects an alternate setting within the USB video streaming interface that uses no bandwidth.


## -prototype


````
PCAM_FREE_BW_ROUTINE_EX CamFreeBandwidthEx;

NTSTATUS CamFreeBandwidthEx(
   PDEVICE_OBJECT BusDeviceObject,
   PVOID          DeviceContext,
   ULONG          StreamNumber
)
{ ... }
````


## -parameters




### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.


### -param DeviceContext

Pointer to the camera minidriver's device context.


### -param STreamNumber








#### - StreamNumber

Indicates stream number.


## -returns



<b>CamFreeBandwidthEx</b> returns STATUS_SUCCESS or an appropriate error code.




## -remarks



USBCAMD calls the camera minidriver's <b>CamFreeBandwidthEx</b> callback function after the isochronous video stream has stopped.

Typically, this function calls the <b>USBCAMD_SelectAlternateInterface</b> service to select the correct alternate interface and prepare for streaming video.

The original USBCAMD does not call <b>CamFreeBandwidthEx</b>.

This function is required.




## -see-also

<a href="..\usbcamdi\nf-usbcamdi-usbcamd_selectalternateinterface.md">USBCAMD_SelectAlternateInterface</a>



<a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data2.md">USBCAMD_DEVICE_DATA2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PCAM_FREE_BW_ROUTINE_EX routine%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

