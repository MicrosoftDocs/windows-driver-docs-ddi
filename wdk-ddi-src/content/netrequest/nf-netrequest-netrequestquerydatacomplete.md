---
UID: NF:netrequest.NetRequestQueryDataComplete
title: NetRequestQueryDataComplete function (netrequest.h)
description: Completes a query data (OID) request.
tech.root: netvista
ms.assetid: f954ca2b-cce7-48ea-ba74-6acfbd3b4cf7
ms.date: 02/08/2018
ms.topic: function
f1_keywords:
 - "netrequest/NetRequestQueryDataComplete"
ms.keywords: NetRequestQueryDataComplete
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
- NetRequestQueryDataComplete
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetRequestQueryDataComplete function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

Completes a query data (OID) request.

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

### -param BytesWritten
The number of bytes that the client driver wrote to the request buffer.

## -returns
This method does not return a value.

## -remarks
Typically, the client driver calls **NetRequestQueryDataComplete** from one of its control request handler routines. For more info, see [Handling Control Requests](https://docs.microsoft.com/windows-hardware/drivers/netcx/handling-control-requests#completing-requests).

After this method returns, the request handle is no longer valid. NetAdapterCx removes it from the NETQUEUE and deletes the NETREQUEST object.



## -see-also

[NetRequestCompleteWithoutInformation](nf-netrequest-netrequestcompletewithoutinformation.md)

[NetRequestMethodComplete](nf-netrequest-netrequestmethodcomplete.md)

[NetRequestSetDataComplete](nf-netrequest-netrequestsetdatacomplete.md)
