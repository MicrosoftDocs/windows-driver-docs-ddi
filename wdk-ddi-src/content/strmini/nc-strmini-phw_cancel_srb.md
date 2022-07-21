---
UID: NC:strmini.PHW_CANCEL_SRB
title: PHW_CANCEL_SRB (strmini.h)
description: The class driver calls the minidriver's StrMiniCancelPacket routine to signal that a stream request has been canceled.
tech.root: stream
ms.date: 04/22/2022
keywords: ["PHW_CANCEL_SRB callback function"]
ms.keywords: PHW_CANCEL_SRB, StrMiniCancelPacket, StrMiniCancelPacket routine [Streaming Media Devices], stream.strminicancelpacket, strmini-routines_976ab3d0-d8aa-4121-a0a8-b37d08a07219.xml, strmini/StrMiniCancelPacket
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PHW_CANCEL_SRB
 - strmini/PHW_CANCEL_SRB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - strmini.h
api_name:
 - PHW_CANCEL_SRB
---

## -description

The class driver calls the minidriver's *StrMiniCancelPacket* routine to signal that a stream request has been canceled.

## -parameters

### -param SRB [in]

Pointer to the stream request that had been canceled.

## -remarks

The minidriver specifies this routine in the **HwCancelPacket** member of its [HW_INITIALIZATION_DATA](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data) structure. The minidriver passes this structure to the class driver when it registers itself by calling [StreamClassRegisterMinidriver](/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassregisteradapter).

Minidrivers that rely on the class driver to handle synchronization should, once they have successfully canceled a request, signal to the class driver that they are ready for another request by using [StreamClassStreamNotification](/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassstreamnotification) or [StreamClassDeviceNotification](/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassdevicenotification) with the appropriate **ReadyForNext***Xxx***Request**.
