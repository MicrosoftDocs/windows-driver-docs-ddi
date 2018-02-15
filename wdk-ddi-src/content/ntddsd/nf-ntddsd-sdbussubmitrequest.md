---
UID: NF:ntddsd.SdBusSubmitRequest
title: SdBusSubmitRequest function
author: windows-driver-content
description: The SdBusSubmitRequest routine sends a synchronous Secure Digital (SD) request to the bus driver.
old-location: sd\sdbussubmitrequest.htm
old-project: SD
ms.assetid: 8f794681-afa9-474b-a3b9-bc7c21c7c423
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: ntddsd/SdBusSubmitRequest, SdBusSubmitRequest function [Buses], sd-rtns_2709a5bb-0cc9-42b0-9fd1-2b8206a383d5.xml, SD.sdbussubmitrequest, SdBusSubmitRequest
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddsd.h
apiname:
-	SdBusSubmitRequest
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# SdBusSubmitRequest function


## -description


The <b>SdBusSubmitRequest</b> routine sends a synchronous Secure Digital (SD) request to the bus driver.


## -syntax


````
NTSTATUS SdBusSubmitRequest(
  _In_ PVOID                 InterfaceContext,
  _In_ PSDBUS_REQUEST_PACKET Sdrp
);
````


## -parameters




### -param InterfaceContext [in]

Contains the context information returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537906">SdBusOpenInterface</a> routine in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/92b8762d-8af3-493c-aa1d-bc245b0cbd83">SDBUS_INTERFACE_STANDARD</a> structure.


### -param Packet

TBD




#### - Sdrp [in]

Pointer to a caller-supplied structure of type <a href="https://msdn.microsoft.com/09b30bf0-fe85-4ad5-bd3e-113ed3a093ac">SDBUS_REQUEST_PACKET</a> that describes the request.


## -returns



Returns STATUS_SUCCESS if the operation succeeds, or the appropriate error code if the operation fails. 




## -remarks



The <b>SdBusSubmitRequest</b> routine completes the request synchronously. It never returns a status code of STATUS_PENDING, but waits for the request to completed before returning.

This routine is a wrapper for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537914">SdBusSubmitRequestAsync</a> routine. 

Callers of <a href="https://msdn.microsoft.com/library/windows/hardware/ff537914">SdBusSubmitRequestAsync</a> must be running at IRQL &lt;= DISPATCH_LEVEL.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537914">SdBusSubmitRequestAsync</a>



<a href="https://msdn.microsoft.com/09b30bf0-fe85-4ad5-bd3e-113ed3a093ac">SDBUS_REQUEST_PACKET</a>



<a href="https://msdn.microsoft.com/92b8762d-8af3-493c-aa1d-bc245b0cbd83">SDBUS_INTERFACE_STANDARD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537906">SdBusOpenInterface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SD\buses]:%20SdBusSubmitRequest function%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

