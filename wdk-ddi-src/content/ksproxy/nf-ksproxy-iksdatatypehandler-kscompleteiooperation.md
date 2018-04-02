---
UID: NF:ksproxy.IKsDataTypeHandler.KsCompleteIoOperation
title: IKsDataTypeHandler::KsCompleteIoOperation method
author: windows-driver-content
description: The KsCompleteIoOperation method cleans up the extended header and completes the input and output (I/O) operation.
old-location: stream\iksdatatypehandler_kscompleteiooperation.htm
old-project: stream
ms.assetid: 46a58007-16bf-422b-8408-30a7b65dbee6
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsDataTypeHandler, IKsDataTypeHandler interface [Streaming Media Devices], KsCompleteIoOperation method, IKsDataTypeHandler::KsCompleteIoOperation, KsCompleteIoOperation method [Streaming Media Devices], KsCompleteIoOperation method [Streaming Media Devices], IKsDataTypeHandler interface, KsCompleteIoOperation,IKsDataTypeHandler.KsCompleteIoOperation, ksproxy/IKsDataTypeHandler::KsCompleteIoOperation, ksproxy_04136093-03d0-4490-bf5c-5e83bddc23c7.xml, stream.iksdatatypehandler_kscompleteiooperation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ksproxy.h
api_name:
-	IKsDataTypeHandler.KsCompleteIoOperation
product:
- Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsDataTypeHandler::KsCompleteIoOperation method


## -description


The <b>KsCompleteIoOperation</b> method cleans up the extended header and completes the input and output (I/O) operation. 


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
 


### -param Cancelled [in]

Boolean value that is <b>TRUE</b> if the I/O operation was canceled and <b>FALSE</b> otherwise.


## -returns



Returns NOERROR if successful; otherwise, returns an error code. If the stream's major type is KSDATAFORMAT_TYPE_AUDIO, a <b>KsCompleteIoOperation</b> call is inapplicable, so <b>KsCompleteIoOperation</b> automatically returns NOERROR.




## -remarks



The client only calls <b>KsCompleteIoOperation</b> if the data type handler indicated to the client the existence of extended header information in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559836">IKsDataTypeHandler::KsQueryExtendedSize</a> method.

For more information about <b>IMediaSample</b>, see the Microsoft Windows SDK documentation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559836">IKsDataTypeHandler::KsQueryExtendedSize</a>
 

 

