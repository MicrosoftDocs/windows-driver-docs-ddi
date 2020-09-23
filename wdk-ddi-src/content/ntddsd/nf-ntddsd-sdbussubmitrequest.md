---
UID: NF:ntddsd.SdBusSubmitRequest
title: SdBusSubmitRequest function (ntddsd.h)
description: The SdBusSubmitRequest routine sends a synchronous Secure Digital (SD) request to the bus driver.
old-location: sd\sdbussubmitrequest.htm
tech.root: SD
ms.assetid: 8f794681-afa9-474b-a3b9-bc7c21c7c423
ms.date: 02/15/2018
keywords: ["SdBusSubmitRequest function"]
ms.keywords: SD.sdbussubmitrequest, SdBusSubmitRequest, SdBusSubmitRequest function [Buses], ntddsd/SdBusSubmitRequest, sd-rtns_2709a5bb-0cc9-42b0-9fd1-2b8206a383d5.xml
req.header: ntddsd.h
req.include-header: Ntddsd.h
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
req.irql: <DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SdBusSubmitRequest
 - ntddsd/SdBusSubmitRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddsd.h
api_name:
 - SdBusSubmitRequest
---

# SdBusSubmitRequest function


## -description

The <b>SdBusSubmitRequest</b> routine sends a synchronous Secure Digital (SD) request to the bus driver.

## -parameters

### -param InterfaceContext 

[in]
Contains the context information returned by the <a href="/windows-hardware/drivers/ddi/ntddsd/nf-ntddsd-sdbusopeninterface">SdBusOpenInterface</a> routine in the <b>Context</b> member of the <a href="/previous-versions/windows/hardware/drivers/ff537923(v=vs.85)">SDBUS_INTERFACE_STANDARD</a> structure.

### -param Packet

<p>Pointer to a caller-supplied structure of type <a href="/previous-versions/windows/hardware/drivers/ff537931(v=vs.85)"><b>SDBUS_REQUEST_PACKET</b></a> that describes the request.</p>

## -returns

Returns STATUS_SUCCESS if the operation succeeds, or the appropriate error code if the operation fails.

## -remarks

The <b>SdBusSubmitRequest</b> routine completes the request synchronously. It never returns a status code of STATUS_PENDING, but waits for the request to completed before returning.

This routine is a wrapper for the <a href="/windows-hardware/drivers/ddi/ntddsd/nf-ntddsd-sdbussubmitrequestasync">SdBusSubmitRequestAsync</a> routine. 

Callers of <a href="/windows-hardware/drivers/ddi/ntddsd/nf-ntddsd-sdbussubmitrequestasync">SdBusSubmitRequestAsync</a> must be running at IRQL <= DISPATCH_LEVEL.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff537923(v=vs.85)">SDBUS_INTERFACE_STANDARD</a>



<a href="/previous-versions/windows/hardware/drivers/ff537931(v=vs.85)">SDBUS_REQUEST_PACKET</a>



<a href="/windows-hardware/drivers/ddi/ntddsd/nf-ntddsd-sdbusopeninterface">SdBusOpenInterface</a>



<a href="/windows-hardware/drivers/ddi/ntddsd/nf-ntddsd-sdbussubmitrequestasync">SdBusSubmitRequestAsync</a>