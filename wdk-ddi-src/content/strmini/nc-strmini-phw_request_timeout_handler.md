---
UID: NC:strmini.PHW_REQUEST_TIMEOUT_HANDLER
title: PHW_REQUEST_TIMEOUT_HANDLER
author: windows-driver-content
description: The stream class driver calls the minidriver's StrMiniRequestTimeout routine to signal to the minidriver that a request has timed out.
old-location: stream\strminirequesttimeout.htm
old-project: stream
ms.assetid: be3972af-1c62-4d4d-95f7-00f894ae7f21
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PHW_REQUEST_TIMEOUT_HANDLER, StrMiniRequestTimeout, StrMiniRequestTimeout routine [Streaming Media Devices], stream.strminirequesttimeout, strmini-routines_74b67060-d244-452f-a5a5-217fd4c65614.xml, strmini/StrMiniRequestTimeout
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
-	StrMiniRequestTimeout
product: Windows
targetos: Windows
req.typenames: ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
req.product: Windows 10 or later.
---

# PHW_REQUEST_TIMEOUT_HANDLER callback


## -description


The stream class driver calls the minidriver's <i>StrMiniRequestTimeout</i> routine to signal to the minidriver that a request has timed out.


## -prototype


````
PHW_REQUEST_TIMEOUT_HANDLER StrMiniRequestTimeout;

VOID StrMiniRequestTimeout(
  _In_ PHW_STREAM_REQUEST_BLOCK pSrb
)
{ ... }
````


## -parameters




### -param SRB








#### - pSrb [in]

Pointer to the stream request that has timed out.


## -returns



None




## -remarks



The minidriver specifies this routine in the <b>HwRequestTimeoutHandler</b> member of its <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure. The minidriver passes this structure to the class driver when it registers itself by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>.

When the class driver first issues a request, it sets a time-out value (in seconds) with the <b>TimeoutCounter</b> member of the <a href="..\strmini\ns-strmini-_hw_stream_request_block.md">HW_STREAM_REQUEST_BLOCK</a> pointed to by <i>pSrb</i>. The class driver decrements the <b>TimeoutCounter</b> member of that structure once a second. A request times out when the class driver decrements <b>TimeoutCounter</b> to zero, at which time the class driver calls <i>StrMiniRequestTimeout</i> to handle any clean-up necessary to cease processing the request.

Minidrivers that rely on the class driver to handle synchronization should, once they have successfully handled the request time-out, signal to the class driver that they are ready for another request by using <a href="..\strmini\nf-strmini-streamclassstreamnotification.md">StreamClassStreamNotification</a> or <a href="..\strmini\nf-strmini-streamclassdevicenotification.md">StreamClassDeviceNotification</a> with the appropriate <b>ReadyForNext</b><i>Xxx</i><b>Request</b>.



