---
UID: NF:ksproxy.IKsDataTypeHandler.KsPrepareIoOperation
title: IKsDataTypeHandler::KsPrepareIoOperation (ksproxy.h)
description: The KsPrepareIoOperation method initializes the extended header and prepares the media sample for an I/O operation.
old-location: stream\iksdatatypehandler_ksprepareiooperation.htm
tech.root: stream
ms.assetid: 16411d58-5fff-430f-b96d-78eed1dbb01c
ms.date: 04/23/2018
ms.keywords: IKsDataTypeHandler interface [Streaming Media Devices],KsPrepareIoOperation method, IKsDataTypeHandler.KsPrepareIoOperation, IKsDataTypeHandler::KsPrepareIoOperation, KsPrepareIoOperation, KsPrepareIoOperation method [Streaming Media Devices], KsPrepareIoOperation method [Streaming Media Devices],IKsDataTypeHandler interface, ksproxy/IKsDataTypeHandler::KsPrepareIoOperation, ksproxy_24b2f3a8-8870-434e-9f15-71fa363d3215.xml, stream.iksdatatypehandler_ksprepareiooperation
f1_keywords:
 - "ksproxy/IKsDataTypeHandler.KsPrepareIoOperation"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ksproxy.h
api_name:
- IKsDataTypeHandler.KsPrepareIoOperation
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsDataTypeHandler::KsPrepareIoOperation


## -description


The <b>KsPrepareIoOperation</b> method initializes the extended header and prepares the media sample for an I/O operation.


## -parameters




### -param Sample [in, out]

Pointer to the <b>IMediaSample</b> interface for the associated media sample.


### -param StreamHeader [in, out]

Pointer to a buffer that contains the extended header information.


### -param IoOperation [in]

Value that specifies the type of I/O operation. This value can be one of the following values from the KSIOOPERATION enumerated type:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>KsIoOperation_Write</b>

</td>
<td>
Write data to stream.

</td>
</tr>
<tr>
<td>
<b>KsIoOperation_Read</b>

</td>
<td>
Read data from stream.

</td>
</tr>
</table>
 


## -returns



Returns NOERROR if successful; otherwise, returns an error code. If the stream's major type is KSDATAFORMAT_TYPE_AUDIO, a <b>KsPrepareIoOperation</b> call is inapplicable, so <b>KsPrepareIoOperation</b> automatically returns NOERROR.




## -remarks



The client only calls <b>KsPrepareIoOperation</b> if the data type handler indicated to the client the existence of extended header information in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksdatatypehandler-ksqueryextendedsize">IKsDataTypeHandler::KsQueryExtendedSize</a> method.

For more information about <b>IMediaSample</b>, see the Microsoft Windows SDK documentation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksdatatypehandler-ksqueryextendedsize">IKsDataTypeHandler::KsQueryExtendedSize</a>
 

 

