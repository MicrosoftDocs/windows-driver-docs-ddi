---
UID: NF:netrequest.NetRequestSetDataComplete
title: NetRequestSetDataComplete function (netrequest.h)
description: Completes a set data (OID) request.
tech.root: netvista
ms.assetid: c0f1aea6-e748-4e42-97ca-d683b9da1281
ms.date: 02/08/2018
keywords: ["NetRequestSetDataComplete function"]
f1_keywords:
 - "netrequest/NetRequestSetDataComplete"
ms.keywords: NetRequestSetDataComplete
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netrequest.h
api_name: 
- NetRequestSetDataComplete
targetos: Windows
product:
- Windows
---

# NetRequestSetDataComplete function


## -description



Completes a set data (OID) request.

## -parameters

### -param Request
A handle to a network request object.

### -param CompletionStatus
An NTSTATUS value that represents the completion status of the request. Valid status values include, but are not limited to, the following:

| Return code | Description |
| --- | --- |
| STATUS_SUCCESS | The driver successfully completed the request. |
| STATUS_CANCELLED | The driver canceled the request. |
| STATUS_UNSUCCESSFUL | The driver encountered an error while processing the request. |

### -param BytesRead
The number of bytes that the client driver read from the request buffer.

## -remarks
Typically, the client driver calls **NetRequestSetDataComplete** from one of its control request handler routines. For more info, see [Handling Control Requests](https://docs.microsoft.com/windows-hardware/drivers/netcx/handling-control-requests#completing-requests).

After this method returns, the request handle is no longer valid. NetAdapterCx removes it from the NETQUEUE and deletes the NETREQUEST object.



## -see-also

[NetRequestCompleteWithoutInformation](nf-netrequest-netrequestcompletewithoutinformation.md)

[NetRequestMethodComplete](nf-netrequest-netrequestmethodcomplete.md)

[NetRequestQueryDataComplete](nf-netrequest-netrequestquerydatacomplete.md)
