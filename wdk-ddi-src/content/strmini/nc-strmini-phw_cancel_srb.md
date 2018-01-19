---
UID: NC:strmini.PHW_CANCEL_SRB
title: PHW_CANCEL_SRB
author: windows-driver-content
description: The class driver calls the minidriver's StrMiniCancelPacket routine to signal that a stream request has been canceled.
old-location: stream\strminicancelpacket.htm
old-project: stream
ms.assetid: e64c00dd-4eef-4e1e-abb0-8263088f6dc6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _ZONE_DESCRIPTIOR, ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
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
req.alt-api: StrMiniCancelPacket
req.alt-loc: strmini.h
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
req.typenames: ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
req.product: Windows 10 or later.
---

# PHW_CANCEL_SRB callback



## -description
The class driver calls the minidriver's <i>StrMiniCancelPacket</i> routine to signal that a stream request has been canceled.



## -prototype

````
PHW_CANCEL_SRB StrMiniCancelPacket;

VOID StrMiniCancelPacket(
  _In_ PHW_STREAM_REQUEST_BLOCK pSrb
)
{ ... }
````


## -parameters

### -param pSrb [in]

Pointer to the stream request that had been canceled.


## -returns
None


## -remarks
The minidriver specifies this routine in the <b>HwCancelPacket</b> member of its <a href="..\strmini\ns-strmini-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure. The minidriver passes this structure to the class driver when it registers itself by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>.

Minidrivers that rely on the class driver to handle synchronization should, once they have successfully canceled a request, signal to the class driver that they are ready for another request by using <a href="..\strmini\nf-strmini-streamclassstreamnotification.md">StreamClassStreamNotification</a> or <a href="..\strmini\nf-strmini-streamclassdevicenotification.md">StreamClassDeviceNotification</a> with the appropriate <b>ReadyForNext</b><i>Xxx</i><b>Request</b>.</p>