---
UID: NF:ksproxy.IKsDataTypeHandler.KsPrepareIoOperation
title: IKsDataTypeHandler::KsPrepareIoOperation (ksproxy.h)
description: The KsPrepareIoOperation method initializes the extended header and prepares the media sample for an I/O operation.
tech.root: stream
ms.date: 03/07/2023
keywords: ["IKsDataTypeHandler::KsPrepareIoOperation"]
ms.keywords: IKsDataTypeHandler interface [Streaming Media Devices],KsPrepareIoOperation method, IKsDataTypeHandler.KsPrepareIoOperation, IKsDataTypeHandler::KsPrepareIoOperation, KsPrepareIoOperation, KsPrepareIoOperation method [Streaming Media Devices], KsPrepareIoOperation method [Streaming Media Devices],IKsDataTypeHandler interface, ksproxy/IKsDataTypeHandler::KsPrepareIoOperation, ksproxy_24b2f3a8-8870-434e-9f15-71fa363d3215.xml, stream.iksdatatypehandler_ksprepareiooperation
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
 - IKsDataTypeHandler::KsPrepareIoOperation
 - ksproxy/IKsDataTypeHandler::KsPrepareIoOperation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsDataTypeHandler::KsPrepareIoOperation
---

## -description

The **KsPrepareIoOperation** method initializes the extended header and prepares the media sample for an I/O operation.

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

## -returns

Returns NOERROR if successful; otherwise, returns an error code. If the stream's major type is KSDATAFORMAT_TYPE_AUDIO, a **KsPrepareIoOperation** call is inapplicable, so **KsPrepareIoOperation** automatically returns NOERROR.

## -remarks

The client only calls **KsPrepareIoOperation** if the data type handler indicated to the client the existence of extended header information in a call to the [IKsDataTypeHandler::KsQueryExtendedSize](/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksdatatypehandler-ksqueryextendedsize) method.

For more information about **IMediaSample**, see the Microsoft Windows SDK documentation.

## -see-also

[IKsDataTypeHandler::KsQueryExtendedSize](/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksdatatypehandler-ksqueryextendedsize)
