---
UID: NC:strmini.PHW_RECEIVE_DEVICE_SRB
title: PHW_RECEIVE_DEVICE_SRB
author: windows-driver-content
description: The stream class driver calls the minidriver's StrMiniReceiveStreamControlPacket routine to handle I/O requests for a specific stream.
old-location: stream\strminireceivestreamdatapacket.htm
old-project: stream
ms.assetid: 4b354e7d-01b9-43b5-8d22-6e15a4ae4958
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.strminireceivestreamdatapacket, StrMiniReceiveStreamDataPacket, StrMiniReceiveStreamDataPacket routine [Streaming Media Devices], StrMiniReceiveStreamDataPacket, PHW_RECEIVE_DEVICE_SRB, PHW_RECEIVE_DEVICE_SRB, strmini/StrMiniReceiveStreamDataPacket, strmini-routines_4e6dca6e-df0a-478e-9655-0b2221621c2e.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	strmini.h
apiname:
-	StrMiniReceiveStreamDataPacket
product: Windows
targetos: Windows
req.typenames: ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
req.product: Windows 10 or later.
---

# PHW_RECEIVE_DEVICE_SRB callback


## -description


The stream class driver calls the minidriver's <i>StrMiniReceiveStreamControlPacket</i> routine to handle I/O requests for a specific stream.


## -prototype


````
PHW_RECEIVE_DEVICE_SRB StrMiniReceiveStreamDataPacket;

VOID StrMiniReceiveStreamDataPacket(
  _In_ PHW_STREAM_REQUEST_BLOCK pSRB
)
{ ... }
````


## -parameters




### -param SRB








#### - pSRB [in]

Pointer to the stream request block.


## -returns



None




## -remarks



The stream class driver calls the minidriver's <i>StrMiniReceiveStreamDataPacket</i> routine to handle read and write requests for a specific stream.

The minidriver registers its <i>StrMiniReceiveStreamDataPacket</i> routine as follows: When the class driver opens the stream, it passes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568191">SRB_OPEN_STREAM</a> request block to the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568463">StrMiniReceiveDevicePacket</a> routine. The StreamObject of the request packet points to a <a href="..\strmini\ns-strmini-_hw_stream_object.md">HW_STREAM_OBJECT</a>. The minidriver sets the <b>ReceiveDataPacket</b> member of the structure pointed to by <i>pSrb</i>-&gt;<b>StreamObject</b> to the minidriver's <i>StrMiniReceiveDataPacket</i> routine. 

Upon completion of its handling of the request, the minidriver passes the structure back to the class driver by calling <a href="..\strmini\nf-strmini-streamclassstreamnotification.md">StreamClassStreamNotification</a><b>(StreamRequestComplete, pSRB-&gt;StreamObject, pSRB)</b>. 

See information about relevant SRB codes in <a href="https://msdn.microsoft.com/library/windows/hardware/ff568295">Stream Class SRB Reference</a>.

When the minidriver finishes its processing of the request, it enters the return status of the operation in <i>pSrb</i>-&gt;<b>Status</b>. The minidriver should enter STATUS_SUCCESS for normal successful processing. If the minidriver does not support that Command value, it should set <i>pSrb</i>-&gt;<b>Status</b> to STATUS_NOT_IMPLEMENTED. If there is a device hardware error that prevents the minidriver from completing the request, it should set <i>pSrb</i>-&gt;<b>Status</b> to STATUS_IO_DEVICE_ERROR. Other error codes the routine uses in specific circumstances are listed above with the specific Command code.



