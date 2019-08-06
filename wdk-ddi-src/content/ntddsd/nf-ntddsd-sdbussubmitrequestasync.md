---
UID: NF:ntddsd.SdBusSubmitRequestAsync
title: SdBusSubmitRequestAsync function (ntddsd.h)
description: The SdBusSubmitRequestAsync routine sends an asynchronous Secure Digital (SD) request to the bus driver interface.
old-location: sd\sdbussubmitrequestasync.htm
tech.root: SD
ms.assetid: c4425ba5-adf7-4734-a400-1a233a441047
ms.date: 02/15/2018
ms.keywords: SD.sdbussubmitrequestasync, SdBusSubmitRequestAsync, SdBusSubmitRequestAsync function [Buses], ntddsd/SdBusSubmitRequestAsync, sd-rtns_69f249eb-f2e8-48fa-8857-b47c732faea6.xml
ms.topic: function
f1_keywords:
 - "ntddsd/SdBusSubmitRequestAsync"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddsd.h
api_name:
- SdBusSubmitRequestAsync
product:
- Windows
targetos: Windows
req.typenames: 
---

# SdBusSubmitRequestAsync function


## -description


The <b>SdBusSubmitRequestAsync</b> routine sends an asynchronous Secure Digital (SD) request to the bus driver interface.


## -parameters




### -param InterfaceContext [in]

Contains the context information returned by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddsd/nf-ntddsd-sdbusopeninterface">SdBusOpenInterface</a> routine in the <b>Context</b> member of the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff537923(v=vs.85)">SDBUS_INTERFACE_STANDARD</a> structure.


### -param Packet [in]

Pointer to a caller-supplied structure of type <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff537931(v=vs.85)">SDBUS_REQUEST_PACKET</a> that describes the request.


### -param Irp [in]

Points to a caller-supplied IRP that the SD library uses to transmit the request packet. The <b>SdBusSubmitRequestAsync</b> routine stores the packet in the next stack location of the IRP, which allows the caller to reuse IRPs created by a driver higher in the stack.


### -param CompletionRoutine [in]

Pointer to a completion routine of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-io_completion_routine">IoCompletion</a> that <b>SdBusSubmitRequestAsync</b> registers for the IRP specified in the <i>Irp </i>parameter.


### -param UserContext [in]

Pointer to context data that the system passes to the completion routine registered for the IRP specified by the <i>Irp </i>parameter.


## -returns



Returns STATUS_SUCCESS or STATUS_PENDING if the operation succeeds, or the appropriate error message if the operation fails.




## -remarks



Callers of <b>SdBusSubmitRequestAsync</b> must be running at IRQL <= DISPATCH_LEVEL.

Callers of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddsd/nf-ntddsd-sdbussubmitrequest">SdBusSubmitRequest</a> must be running at IRQL < DISPATCH_LEVEL.

This request is handled asynchronously and might return STATUS_PENDING. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff537931(v=vs.85)">SDBUS_REQUEST_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddsd/nf-ntddsd-sdbusopeninterface">SdBusOpenInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddsd/nf-ntddsd-sdbussubmitrequest">SdBusSubmitRequest</a>
 

 

