---
UID: NF:netrequest.NetRequestSetBytesNeeded
title: NetRequestSetBytesNeeded function
author: windows-driver-content
description: Sets the number of bytes needed to read or write for a control request (OID).
ms.assetid: 605c07f1-bc0a-4a84-adf9-b86c6ffcecca
ms.author: windowsdriverdev
ms.date: 02/08/2018
ms.topic: function
ms.keywords: NetRequestSetBytesNeeded
req.header: netrequest.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: <= DISPATCH_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netrequest.h
apiname: 
-	NetRequestSetBytesNeeded
product:
-	Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetRequestSetBytesNeeded function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Sets the number of bytes needed to read or write for a control request (OID).

## -parameters

### -param Request
A handle to a network request object.

### -param BytesNeeded
The number of bytes to be read or written.

## -returns
This method does not return a value.

## -remarks
The client calls this routine if the I/O request fails due a smaller than expected InputOutputBuffer size. For example, to report that 8 bytes are required to support the requested OID:

```c++
status = STATUS_BUFFER_TOO_SMALL;
NetRequestSetBytesNeeded(Request, sizeof(ULONG64));
```

Depending on the request type, *BytesNeeded* may mean space required perform a read operation or a write operation. 

After calling **NetRequestSetBytesNeeded**, the client calls one of the following methods, or [NetRequestCompleteWithoutInformation](nf-netrequest-netrequestcompletewithoutinformation.md):

- [NetRequestMethodComplete](nf-netrequest-netrequestmethodcomplete.md)
- [NetRequestQueryDataComplete](nf-netrequest-netrequestquerydatacomplete.md)
- [NetRequestSetDataComplete](nf-netrequest-netrequestsetdatacomplete.md)

For general info about control requests, see [Handling Control Requests](https://docs.microsoft.com/windows-hardware/drivers/netcx/handling-control-requests).



## -see-also