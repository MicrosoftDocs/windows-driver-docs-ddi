---
UID: NF:netrequest.NetRequestCompleteWithoutInformation
title: NetRequestCompleteWithoutInformation function (netrequest.h)
description: Completes a NETREQUEST and supplies a completion status.
tech.root: netvista
ms.assetid: 706adc5b-3eb4-4876-ad86-6d335a0860ca
ms.date: 02/08/2018
ms.topic: function
f1_keywords:
 - "netrequest/NetRequestCompleteWithoutInformation"
ms.keywords: NetRequestCompleteWithoutInformation
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
- NetRequestCompleteWithoutInformation
targetos: Windows
product:
- Windows
---

# NetRequestCompleteWithoutInformation function


## -description



Completes a NETREQUEST and supplies a completion status.

## -parameters

### -param Request
A handle to a network request object that represents the control (OID) request that is being completed.

### -param CompletionStatus
An NTSTATUS value that represents the completion status of the request. Valid status values include, but are not limited to, the following:

| Return code | Description |
| --- | --- |
| STATUS_SUCCESS | The driver successfully completed the request. |
| STATUS_CANCELLED | The driver canceled the request. |
| STATUS_UNSUCCESSFUL | The driver encountered an error while processing the request. |

## -remarks
Typically, the client driver calls **NetRequestCompleteWithoutInformation** from one of its control request handler routines. Call this function when completing a request that does not require additional memory transfer. For more info, see [Handling Control Requests](https://docs.microsoft.com/windows-hardware/drivers/netcx/handling-control-requests#completing-requests).

After this method returns, the request handle is no longer valid. NetAdapterCx removes it from the NETQUEUE and deletes the NETREQUEST object.



## -see-also

[NetRequestMethodComplete](nf-netrequest-netrequestmethodcomplete.md)

[NetRequestQueryDataComplete](nf-netrequest-netrequestquerydatacomplete.md)

[NetRequestSetDataComplete](nf-netrequest-netrequestsetdatacomplete.md) 
