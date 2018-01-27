---
UID: NF:usbcamdi.USBCAMD_InitializeNewInterface
title: USBCAMD_InitializeNewInterface function
author: windows-driver-content
description: The USBCAMD_InitializeNewInterface function provides USBCAMD with all the necessary information to configure the camera minidriver to work correctly with the stream class driver and the USB bus driver.
old-location: stream\usbcamd_initializenewinterface.htm
old-project: stream
ms.assetid: d0796a9b-9823-4f13-b2df-1fc8ca74cbd1
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: USBCAMD_InitializeNewInterface, stream.usbcamd_initializenewinterface, usbcmdpr_4b43d8ab-fd5f-4199-afbc-b21801c4fab3.xml, USBCAMD_InitializeNewInterface function [Streaming Media Devices], usbcamdi/USBCAMD_InitializeNewInterface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: Usbcamd2.lib
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	usbcamd2.lib
-	usbcamd2.dll
apiname: 
-	USBCAMD_InitializeNewInterface
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# USBCAMD_InitializeNewInterface function


## -description


The <b>USBCAMD_InitializeNewInterface</b> function provides USBCAMD with all the necessary information to configure the camera minidriver to work correctly with the stream class driver and the USB bus driver.


## -syntax


````
ULONG USBCAMD_InitializeNewInterface(
  _In_ PVOID DeviceContext,
  _In_ PVOID DeviceData,
  _In_ ULONG Version,
  _In_ ULONG CamControlFlag
);
````


## -parameters




### -param DeviceContext [in]

Pointer to device-specific context.


### -param DeviceData [in]

Pointer to a <a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data2.md">USBCAMD_DEVICE_DATA2</a> structure.


### -param Version [in]

Specifies the version information. This value should be set to the value USBCAMD_VERSION_200 for use with USBCAMD version 2.0.


### -param CamControlFlag [in]

Specifies how USBCAMD and the camera minidriver should interact. The camera minidriver should set this value to one or more of the following:
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
USBCAMD_CamControlFlag_NoVideoRawProcessing

</td>
<td>
If the camera minidriver does not need to operate on video, it should set the USBCAMD_CamControlFlag_NoVideoRawProcessing. This eliminates one buffer copy.

</td>
</tr>
<tr>
<td>
USBCAMD_CamControlFlag_NoStillRawProcessing

</td>
<td>
If the camera minidriver does not need to operate on the still image raw frame, it should set the USBCAMD_CamControlFlag_NoStillRawProcessing bit to eliminate one buffer copy.

</td>
</tr>
<tr>
<td>
USBCAMD_CamControlFlag_AssociatedFormat

</td>
<td>
The USBCAMD_CamControlFlag_AssociatedFormat bit should be set if the camera minidriver uses the same format for video as it does on the virtual still pin. After this flag is set, USBCAMD does not permit the virtual still pin to be opened in a format different from the video pin. The USBCAMD_CamControlFlag_AssociatedFormat bit should be set only when the virtual still pin produces frames of the same format as the video frames.

</td>
</tr>
<tr>
<td>
USBCAMD_CamControlFlag_EnableDeviceEvents

</td>
<td>
Setting the USBCAMD_CamControlFlag_EnableDeviceEvents exposes a device event to the stream class driver and Microsoft DirectShow. This enables an STI monitor to launch a still image application if the still button is pressed on the camera. USBCAMD sends a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561912">KSEVENT_VIDCAPTOSTI_EXT_TRIGGER</a> event if this bit is set and the camera's still button is pressed.

</td>
</tr>
</table> 


## -returns


<b>USBCAMD_InitializeNewInterface</b> returns the value USBCAMD_VERSION_200.



## -remarks


This function is only called by USBCAMD version 2.0.

The <b>USBCAMD_InitializeNewInterface</b> function must be called by the camera minidriver upon receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff568185">SRB_INITIALIZE_DEVICE</a> request. 



## -see-also

<a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data2.md">USBCAMD_DEVICE_DATA2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568185">SRB_INITIALIZE_DEVICE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20USBCAMD_InitializeNewInterface function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

