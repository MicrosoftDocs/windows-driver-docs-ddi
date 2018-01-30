---
UID: NF:ntddsd.SdBusSubmitRequestAsync
title: SdBusSubmitRequestAsync function
author: windows-driver-content
description: The SdBusSubmitRequestAsync routine sends an asynchronous Secure Digital (SD) request to the bus driver interface.
old-location: sd\sdbussubmitrequestasync.htm
old-project: SD
ms.assetid: c4425ba5-adf7-4734-a400-1a233a441047
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: SD.sdbussubmitrequestasync, ntddsd/SdBusSubmitRequestAsync, sd-rtns_69f249eb-f2e8-48fa-8857-b47c732faea6.xml, SdBusSubmitRequestAsync, SdBusSubmitRequestAsync function [Buses]
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddsd.h
apiname:
-	SdBusSubmitRequestAsync
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# SdBusSubmitRequestAsync function


## -description


The <b>SdBusSubmitRequestAsync</b> routine sends an asynchronous Secure Digital (SD) request to the bus driver interface.


## -syntax


````
NTSTATUS SdBusSubmitRequestAsync(
  _In_ PVOID                  InterfaceContext,
  _In_ PSDBUS_REQUEST_PACKET  Packet,
  _In_ PIRP                   Irp,
  _In_ PIO_COMPLETION_ROUTINE CompletionRoutine,
  _In_ PVOID                  UserContext
);
````


## -parameters




### -param InterfaceContext [in]

Contains the context information returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537906">SdBusOpenInterface</a> routine in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/92b8762d-8af3-493c-aa1d-bc245b0cbd83">SDBUS_INTERFACE_STANDARD</a> structure.


### -param Packet [in]

Pointer to a caller-supplied structure of type <a href="https://msdn.microsoft.com/09b30bf0-fe85-4ad5-bd3e-113ed3a093ac">SDBUS_REQUEST_PACKET</a> that describes the request.


### -param Irp [in]

Points to a caller-supplied IRP that the SD library uses to transmit the request packet. The <b>SdBusSubmitRequestAsync</b> routine stores the packet in the next stack location of the IRP, which allows the caller to reuse IRPs created by a driver higher in the stack.


### -param CompletionRoutine [in]

Pointer to a completion routine of type <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> that <b>SdBusSubmitRequestAsync</b> registers for the IRP specified in the <i>Irp </i>parameter.


### -param UserContext [in]

Pointer to context data that the system passes to the completion routine registered for the IRP specified by the <i>Irp </i>parameter.


## -returns


Returns STATUS_SUCCESS or STATUS_PENDING if the operation succeeds, or the appropriate error message if the operation fails.



## -remarks


Callers of <b>SdBusSubmitRequestAsync</b> must be running at IRQL &lt;= DISPATCH_LEVEL.

Callers of <a href="https://msdn.microsoft.com/library/windows/hardware/ff537909">SdBusSubmitRequest</a> must be running at IRQL &lt; DISPATCH_LEVEL.

This request is handled asynchronously and might return STATUS_PENDING. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537906">SdBusOpenInterface</a>

<a href="https://msdn.microsoft.com/09b30bf0-fe85-4ad5-bd3e-113ed3a093ac">SDBUS_REQUEST_PACKET</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537909">SdBusSubmitRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SD\buses]:%20SdBusSubmitRequestAsync function%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

