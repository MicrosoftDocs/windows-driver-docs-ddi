---
UID: NC:strmini.PHW_RECEIVE_DEVICE_SRB
title: PHW_RECEIVE_DEVICE_SRB
author: windows-driver-content
description: The minidriver-supplied routine handles class driver requests that apply to the driver as a whole, such as initializing the device, or opening a stream within the device.
old-location: stream\strminireceivedevicepacket.htm
old-project: stream
ms.assetid: 51d8a18d-cd90-4fac-a991-6c0de505576e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PHW_RECEIVE_DEVICE_SRB, StrMiniReceiveDevicePacket, StrMiniReceiveDevicePacket routine [Streaming Media Devices], stream.strminireceivedevicepacket, strmini-routines_5c9f03d0-a2b0-4078-8ef8-d84cf150355c.xml, strmini/StrMiniReceiveDevicePacket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: strmini.h
req.include-header: Strmini.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	strmini.h
api_name:
-	StrMiniReceiveDevicePacket
product: Windows
targetos: Windows
req.typenames: ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
req.product: Windows 10 or later.
---

# PHW_RECEIVE_DEVICE_SRB callback


## -description


<i>The minidriver-supplied </i> routine handles class driver requests that apply to the driver as a whole, such as initializing the device, or opening a stream within the device.


## -parameters




### -param SRB








#### - pSRB [in]

Pointer to the stream request block.


## -returns



None




## -remarks



The minidriver specifies this routine in the <b>HwReceivePacket</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff559682">HW_INITIALIZATION_DATA</a> structure. The minidriver passes this structure to the class driver when it registers itself by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>.

<i>StrMiniReceiveDevicePacket</i> must handle class driver requests that apply to the driver as a whole, such as initializing the device, or opening a stream within the device. The class driver passes its information in the form of a pointer to a stream request block. The class driver fills in some of the entries in the stream request block. The minidriver, upon completion of the routine, must fill in additional information that the class driver will use to continue processing. 

Upon completion of its handling of the request, the minidriver passes the structure back to the class driver by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff568239">StreamClassDeviceNotification</a><b>(DeviceRequestComplete, pSRB-&gt;HwDeviceExtension, pSRB)</b>. 

See information about relevant SRB codes in <a href="https://msdn.microsoft.com/library/windows/hardware/ff568295">Stream Class SRB Reference</a>.

When the minidriver finishes its processing of the request, it enters the return status of the operation in <i>pSrb</i>-&gt;<b>Status</b>. The minidriver should enter STATUS_SUCCESS for normal successful processing. If the minidriver does not support that Command value, it should set <i>pSrb</i>-&gt;<b>Status</b> to STATUS_NOT_IMPLEMENTED. If there is a device hardware error that prevents the minidriver from completing the request, it should set <i>pSrb</i>-&gt;<b>Status</b> to STATUS_IO_DEVICE_ERROR. Other error codes the routine uses in specific circumstances are listed above with the specific Command code.

Note that the class driver passes read and write requests to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568470">StrMiniReceiveStreamDataPacket</a> routine.

The minidriver registers its <i>StrMiniReceiveStreamControlPacket</i> routine as follows: When the class driver opens the stream, it passes an <a href="https://msdn.microsoft.com/library/windows/hardware/ff568191">SRB_OPEN_STREAM</a> request block to the minidriver's <i>StrMiniReceiveDevicePacket</i> routine. The <b>StreamObject</b> member of the request packet points to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff559697">HW_STREAM_OBJECT</a>. The minidriver sets the <b>ReceiveControlPacket</b> member of the structure pointed to by <b>StreamObject</b> to the minidriver's <i>StrMiniReceiveControlPacket</i> routine. 

Upon completion of its handling of the request, the minidriver passes the structure back to the class driver by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff568266">StreamClassStreamNotification</a><b>(StreamRequestComplete, pSRB-&gt;StreamObject, pSRB)</b>. 

See information about relevant SRB codes in <a href="https://msdn.microsoft.com/library/windows/hardware/ff568295">Stream Class SRB Reference</a>.

When the minidriver finishes its processing of the request, it enters the return status of the operation in <i>pSrb</i>-&gt;<b>Status</b>. The minidriver should enter STATUS_SUCCESS for normal successful processing. If the minidriver does not support that Command value, it should set <i>pSrb</i>-&gt;<b>Status</b> to STATUS_NOT_IMPLEMENTED. If there is a device hardware error that prevents the minidriver from completing the request, it should set <i>pSrb</i>-&gt;<b>Status</b> to STATUS_IO_DEVICE_ERROR. Other error codes the routine uses in specific circumstances are listed above with the specific Command code.

The stream class driver calls the minidriver's <i>StrMiniReceiveStreamDataPacket</i> routine to handle read and write requests for a specific stream.

The minidriver registers its <i>StrMiniReceiveStreamDataPacket</i> routine as follows: When the class driver opens the stream, it passes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568191">SRB_OPEN_STREAM</a> request block to the minidriver's <i>StrMiniReceiveDevicePacket</i> routine. The StreamObject of the request packet points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff559697">HW_STREAM_OBJECT</a>. The minidriver sets the <b>ReceiveDataPacket</b> member of the structure pointed to by <i>pSrb</i>-&gt;<b>StreamObject</b> to the minidriver's <i>StrMiniReceiveDataPacket</i> routine. 

Upon completion of its handling of the request, the minidriver passes the structure back to the class driver by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff568266">StreamClassStreamNotification</a><b>(StreamRequestComplete, pSRB-&gt;StreamObject, pSRB)</b>. 

See information about relevant SRB codes in <a href="https://msdn.microsoft.com/library/windows/hardware/ff568295">Stream Class SRB Reference</a>.

When the minidriver finishes its processing of the request, it enters the return status of the operation in <i>pSrb</i>-&gt;<b>Status</b>. The minidriver should enter STATUS_SUCCESS for normal successful processing. If the minidriver does not support that Command value, it should set <i>pSrb</i>-&gt;<b>Status</b> to STATUS_NOT_IMPLEMENTED. If there is a device hardware error that prevents the minidriver from completing the request, it should set <i>pSrb</i>-&gt;<b>Status</b> to STATUS_IO_DEVICE_ERROR. Other error codes the routine uses in specific circumstances are listed above with the specific Command code.



