---
UID: NF:usbcamdi.USBCAMD_AdapterReceivePacket
title: USBCAMD_AdapterReceivePacket function
author: windows-driver-content
description: The USBCAMD_AdapterReceivePacket function allows USBCAMD to process an adapter-based stream request block (SRB).
old-location: stream\usbcamd_adapterreceivepacket.htm
old-project: stream
ms.assetid: 12a5ca64-7187-4a70-83ca-0ade6a8b1343
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: USBCAMD_AdapterReceivePacket
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
req.alt-api: USBCAMD_AdapterReceivePacket
req.alt-loc: usbcamd2.lib,usbcamd2.dll
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
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# USBCAMD_AdapterReceivePacket function



## -description
The <b>USBCAMD_AdapterReceivePacket</b> function allows USBCAMD to process an adapter-based stream request block (SRB).



## -syntax

````
PVOID USBCAMD_AdapterReceivePacket(
  _In_ PHW_STREAM_REQUEST_BLOCK Srb,
  _In_ PUSBCAMD_DEVICE_DATA     DeviceData,
  _In_ PDEVICE_OBJECT           *DeviceObject,
  _In_ BOOLEAN                  NeedsCompletion
);
````


## -parameters

### -param Srb [in]

Pointer to the SRB passed to the camera minidriver's <a href="..\usbcamdi\nc-usbcamdi-padapter_receive_packet_routine.md">AdapterReceivePacket</a> callback function.


### -param DeviceData [in]

Pointer to the <a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a> structure that contains entry points to the camera minidriver's callback functions.


### -param DeviceObject [in]

Pointer to the device's physical device object (PDO).


### -param NeedsCompletion [in]

Specifies if USBCAMD is to process and complete the SRB request. Specify <b>TRUE</b> if USBCAMD is to complete the SRB request Specify <b>FALSE</b> to make USBCAMD ignore the SRB request and return the device context pointer.


## -returns
<b>USBCAMD_AdapterReceivePacket</b> returns a pointer to the device-specific context for this instance of the camera.


## -remarks
Typically, this function is called by the camera minidriver from its <a href="..\usbcamdi\nc-usbcamdi-padapter_receive_packet_routine.md">AdapterReceivePacket</a> routine. 

This function can also be used by the minidriver to retrieve the device context by setting the <i>NeedsCompletion</i> parameter to <b>FALSE</b>. In this case, the <i>DeviceData</i> and <i>DeviceObject</i> parameters are ignored.


## -see-also
<dl>
<dt>
<a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a>
</dt>
<dt>
<a href="..\usbcamdi\nc-usbcamdi-padapter_receive_packet_routine.md">AdapterReceivePacket</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20USBCAMD_AdapterReceivePacket function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

