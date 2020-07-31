---
UID: NC:strmini.PHW_CANCEL_SRB
title: PHW_CANCEL_SRB (strmini.h)
description: The class driver calls the minidriver's StrMiniCancelPacket routine to signal that a stream request has been canceled.
old-location: stream\strminicancelpacket.htm
tech.root: stream
ms.assetid: e64c00dd-4eef-4e1e-abb0-8263088f6dc6
ms.date: 04/23/2018
keywords: ["PHW_CANCEL_SRB callback function"]
ms.keywords: PHW_CANCEL_SRB, StrMiniCancelPacket, StrMiniCancelPacket routine [Streaming Media Devices], stream.strminicancelpacket, strmini-routines_976ab3d0-d8aa-4121-a0a8-b37d08a07219.xml, strmini/StrMiniCancelPacket
f1_keywords:
 - "strmini/StrMiniCancelPacket"
 - "StrMiniCancelPacket"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- strmini.h
api_name:
- StrMiniCancelPacket
targetos: Windows
req.typenames: 
---

# PHW_CANCEL_SRB callback function


## -description


The class driver calls the minidriver's <i>StrMiniCancelPacket</i> routine to signal that a stream request has been canceled.


## -parameters




### -param SRB








#### - pSrb [in]

Pointer to the stream request that had been canceled.


## -remarks



The minidriver specifies this routine in the <b>HwCancelPacket</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> structure. The minidriver passes this structure to the class driver when it registers itself by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassregisteradapter">StreamClassRegisterMinidriver</a>.

Minidrivers that rely on the class driver to handle synchronization should, once they have successfully canceled a request, signal to the class driver that they are ready for another request by using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassstreamnotification">StreamClassStreamNotification</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassdevicenotification">StreamClassDeviceNotification</a> with the appropriate <b>ReadyForNext</b><i>Xxx</i><b>Request</b>.



