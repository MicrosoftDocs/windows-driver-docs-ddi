---
UID: NF:ksproxy.IKsDataTypeHandler.KsCompleteIoOperation
title: IKsDataTypeHandler::KsCompleteIoOperation method
author: windows-driver-content
description: The KsCompleteIoOperation method cleans up the extended header and completes the input and output (I/O) operation.
old-location: stream\iksdatatypehandler_kscompleteiooperation.htm
old-project: stream
ms.assetid: 46a58007-16bf-422b-8408-30a7b65dbee6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsDataTypeHandler, IKsDataTypeHandler::KsCompleteIoOperation, KsCompleteIoOperation
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
req.alt-api: IKsDataTypeHandler.KsCompleteIoOperation
req.alt-loc: ksproxy.h
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
req.typenames: PIPE_STATE
---

# IKsDataTypeHandler::KsCompleteIoOperation method



## -description
The <b>KsCompleteIoOperation</b> method cleans up the extended header and completes the input and output (I/O) operation. 



## -syntax

````
HRESULT KsCompleteIoOperation(
  [in, out] IMediaSample  *Sample,
  [in, out] PVOID         StreamHeader,
  [in]      KSIOOPERATION IoOperation,
  [in]      BOOL          Cancelled
);
````


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
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559836">IKsDataTypeHandler::KsQueryExtendedSize</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsDataTypeHandler::KsCompleteIoOperation method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

