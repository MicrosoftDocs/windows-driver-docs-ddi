---
UID: NC:strmini.PHW_REQUEST_TIMEOUT_HANDLER
title: PHW_REQUEST_TIMEOUT_HANDLER (strmini.h)
description: The stream class driver calls the minidriver's StrMiniRequestTimeout routine to signal to the minidriver that a request has timed out.
old-location: stream\strminirequesttimeout.htm
tech.root: stream
ms.assetid: be3972af-1c62-4d4d-95f7-00f894ae7f21
ms.date: 04/23/2018
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
 - StrMiniRequestTimeout
---

# PHW_REQUEST_TIMEOUT_HANDLER callback function


## -description

The stream class driver calls the minidriver's <i>StrMiniRequestTimeout</i> routine to signal to the minidriver that a request has timed out.

## -parameters

### -param SRB

#### - pSrb [in]

Pointer to the stream request that has timed out.

## -remarks

The minidriver specifies this routine in the <b>HwRequestTimeoutHandler</b> member of its <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> structure. The minidriver passes this structure to the class driver when it registers itself by calling <a href="/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassregisteradapter">StreamClassRegisterMinidriver</a>.

When the class driver first issues a request, it sets a time-out value (in seconds) with the <b>TimeoutCounter</b> member of the <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_request_block">HW_STREAM_REQUEST_BLOCK</a> pointed to by <i>pSrb</i>. The class driver decrements the <b>TimeoutCounter</b> member of that structure once a second. A request times out when the class driver decrements <b>TimeoutCounter</b> to zero, at which time the class driver calls <i>StrMiniRequestTimeout</i> to handle any clean-up necessary to cease processing the request.

Minidrivers that rely on the class driver to handle synchronization should, once they have successfully handled the request time-out, signal to the class driver that they are ready for another request by using <a href="/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassstreamnotification">StreamClassStreamNotification</a> or <a href="/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassdevicenotification">StreamClassDeviceNotification</a> with the appropriate <b>ReadyForNext</b><i>Xxx</i><b>Request</b>.