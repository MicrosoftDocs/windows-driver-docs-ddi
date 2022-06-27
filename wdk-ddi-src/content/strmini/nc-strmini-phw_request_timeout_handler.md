---
UID: NC:strmini.PHW_REQUEST_TIMEOUT_HANDLER
title: PHW_REQUEST_TIMEOUT_HANDLER (strmini.h)
description: The stream class driver calls the minidriver's StrMiniRequestTimeout routine to signal to the minidriver that a request has timed out.
tech.root: stream
ms.date: 04/22/2022
keywords: ["PHW_REQUEST_TIMEOUT_HANDLER callback function"]
ms.keywords: PHW_REQUEST_TIMEOUT_HANDLER, StrMiniRequestTimeout, StrMiniRequestTimeout routine [Streaming Media Devices], stream.strminirequesttimeout, strmini-routines_74b67060-d244-452f-a5a5-217fd4c65614.xml, strmini/StrMiniRequestTimeout
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
 - PHW_REQUEST_TIMEOUT_HANDLER
 - strmini/PHW_REQUEST_TIMEOUT_HANDLER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - strmini.h
api_name:
 - PHW_REQUEST_TIMEOUT_HANDLER
---

## -description

The stream class driver calls the minidriver's *StrMiniRequestTimeout* routine to signal to the minidriver that a request has timed out.

## -parameters

### -param SRB [in]

Pointer to the stream request that has timed out.

## -remarks

The minidriver specifies this routine in the **HwRequestTimeoutHandler** member of its [HW_INITIALIZATION_DATA](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data) structure. The minidriver passes this structure to the class driver when it registers itself by calling [StreamClassRegisterMinidriver](/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassregisteradapter).

When the class driver first issues a request, it sets a time-out value (in seconds) with the **TimeoutCounter** member of the [HW_STREAM_REQUEST_BLOCK](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_request_block) pointed to by *SRB*. The class driver decrements the **TimeoutCounter** member of that structure once a second. A request times out when the class driver decrements **TimeoutCounter** to zero, at which time the class driver calls *StrMiniRequestTimeout* to handle any clean-up necessary to cease processing the request.

Minidrivers that rely on the class driver to handle synchronization should, once they have successfully handled the request time-out, signal to the class driver that they are ready for another request by using [StreamClassStreamNotification](/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassstreamnotification) or [StreamClassDeviceNotification](/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassdevicenotification) with the appropriate **ReadyForNext***Xxx***Request**.
