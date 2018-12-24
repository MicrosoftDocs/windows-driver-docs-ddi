---
UID: NF:netrequest.NetRequestRetrieveInputOutputBuffer
title: NetRequestRetrieveInputOutputBuffer function
description: Retrieves the input/output buffer associated with a NETREQUEST object.
tech.root: netvista
ms.assetid: 1ad27440-ca21-4600-a115-285cd72baf2c
ms.date: 02/08/2018
ms.topic: function
ms.keywords: NetRequestRetrieveInputOutputBuffer
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
-	NetRequestRetrieveInputOutputBuffer
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NetRequestRetrieveInputOutputBuffer function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Retrieves the input/output buffer associated with a NETREQUEST object.

## -parameters

### -param Request
A handle to a network request object.

### -param MininumInputLengthRequired
The minimum input length needed for *InputOutputBuffer*. If the buffer's *InputOutputBuffer* is less than the minimum required, this routine returns STATUS_BUFFER_TOO_SMALL.

### -param MininumOutputLengthRequired
The minimum output length needed for *InputOutputBuffer*. If the buffer's *OutputBufferLength* is less than the minimum required, this routine returns STATUS_BUFFER_TOO_SMALL.

### -param InputOutputBuffer
Address to a location that receives a pointer to the buffer.

### -param InputBufferLength
Address to a location that receives the actual input length of *InputOutputBuffer*.

### -param OutputBufferLength
Address to a location that receives the actual output length of *InputOutputBuffer*.

## -returns
The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks


## -see-also
