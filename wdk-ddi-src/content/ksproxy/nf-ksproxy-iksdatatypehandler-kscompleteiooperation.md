---
UID: NF:ksproxy.IKsDataTypeHandler.KsCompleteIoOperation
title: IKsDataTypeHandler::KsCompleteIoOperation (ksproxy.h)
description: The KsCompleteIoOperation method cleans up the extended header and completes the input and output (I/O) operation.
tech.root: stream
ms.date: 03/07/2023
keywords: ["IKsDataTypeHandler::KsCompleteIoOperation"]
ms.keywords: IKsDataTypeHandler interface [Streaming Media Devices],KsCompleteIoOperation method, IKsDataTypeHandler.KsCompleteIoOperation, IKsDataTypeHandler::KsCompleteIoOperation, KsCompleteIoOperation, KsCompleteIoOperation method [Streaming Media Devices], KsCompleteIoOperation method [Streaming Media Devices],IKsDataTypeHandler interface, ksproxy/IKsDataTypeHandler::KsCompleteIoOperation, ksproxy_04136093-03d0-4490-bf5c-5e83bddc23c7.xml, stream.iksdatatypehandler_kscompleteiooperation
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IKsDataTypeHandler::KsCompleteIoOperation
 - ksproxy/IKsDataTypeHandler::KsCompleteIoOperation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsDataTypeHandler::KsCompleteIoOperation
---

## -description

The **KsCompleteIoOperation** method cleans up the extended header and completes the input and output (I/O) operation.

## -parameters

### -param Sample [in, out]

Pointer to the **IMediaSample** interface for the associated media sample.

### -param StreamHeader [in, out]

Pointer to a buffer that contains the extended header information.

### -param IoOperation [in]

Value that specifies the type of I/O operation. This value can be one of the following values from the KSIOOPERATION enumerated type:

| Value | Description |
|---|---|
| **KsIoOperation_Write** | Write data to stream. |
| **KsIoOperation_Read** | Read data from stream. |

### -param Cancelled [in]

Boolean value that is **TRUE** if the I/O operation was canceled and **FALSE** otherwise.

## -returns

Returns NOERROR if successful; otherwise, returns an error code. If the stream's major type is KSDATAFORMAT_TYPE_AUDIO, a **KsCompleteIoOperation** call is inapplicable, so **KsCompleteIoOperation** automatically returns NOERROR.

## -remarks

The client only calls **KsCompleteIoOperation** if the data type handler indicated to the client the existence of extended header information in a call to the [IKsDataTypeHandler::KsQueryExtendedSize](./nf-ksproxy-iksdatatypehandler-ksqueryextendedsize.md) method.

For more information about **IMediaSample**, see the Microsoft Windows SDK documentation.

## -see-also

[IKsDataTypeHandler::KsQueryExtendedSize](./nf-ksproxy-iksdatatypehandler-ksqueryextendedsize.md)