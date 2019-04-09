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
req.irql: "<=DISPATCH_LEVEL"
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

Contains the context information returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537906">SdBusOpenInterface</a> routine in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/92b8762d-8af3-493c-aa1d-bc245b0cbd83">SDBUS_INTERFACE_STANDARD</a> structure.


### -param Packet [in]

Pointer to a caller-supplied structure of type <a href="https://msdn.microsoft.com/09b30bf0-fe85-4ad5-bd3e-113ed3a093ac">SDBUS_REQUEST_PACKET</a> that describes the request.


### -param Irp [in]

Points to a caller-supplied IRP that the SD library uses to transmit the request packet. The <b>SdBusSubmitRequestAsync</b> routine stores the packet in the next stack location of the IRP, which allows the caller to reuse IRPs created by a driver higher in the stack.


### -param CompletionRoutine [in]

Pointer to a completion routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> that <b>SdBusSubmitRequestAsync</b> registers for the IRP specified in the <i>Irp </i>parameter.


### -param UserContext [in]

Pointer to context data that the system passes to the completion routine registered for the IRP specified by the <i>Irp </i>parameter.


## -returns



Returns STATUS_SUCCESS or STATUS_PENDING if the operation succeeds, or the appropriate error message if the operation fails.




## -remarks



Callers of <b>SdBusSubmitRequestAsync</b> must be running at IRQL &lt;= DISPATCH_LEVEL.

Callers of <a href="https://msdn.microsoft.com/library/windows/hardware/ff537909">SdBusSubmitRequest</a> must be running at IRQL &lt; DISPATCH_LEVEL.

This request is handled asynchronously and might return STATUS_PENDING. 




## -see-also




<a href="https://msdn.microsoft.com/09b30bf0-fe85-4ad5-bd3e-113ed3a093ac">SDBUS_REQUEST_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537906">SdBusOpenInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537909">SdBusSubmitRequest</a>
 

 

