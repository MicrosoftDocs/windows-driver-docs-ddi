---
UID: NF:ksproxy.IKsDataTypeHandler.KsQueryExtendedSize
title: IKsDataTypeHandler::KsQueryExtendedSize method
author: windows-driver-content
description: The KsQueryExtendedSize method retrieves extended header information required for input and output (I/O) operations.
old-location: stream\iksdatatypehandler_ksqueryextendedsize.htm
old-project: stream
ms.assetid: 14d03e6f-d02c-4b39-8f21-b339c65fb036
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsQueryExtendedSize method [Streaming Media Devices], IKsDataTypeHandler interface, ksproxy/IKsDataTypeHandler::KsQueryExtendedSize, ksproxy_b76ac8b2-6bf7-4839-9783-35c865efeb29.xml, KsQueryExtendedSize, IKsDataTypeHandler interface [Streaming Media Devices], KsQueryExtendedSize method, IKsDataTypeHandler::KsQueryExtendedSize, IKsDataTypeHandler, stream.iksdatatypehandler_ksqueryextendedsize, KsQueryExtendedSize method [Streaming Media Devices]
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
req.lib: ksproxy.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ksproxy.h
apiname:
-	IKsDataTypeHandler.KsQueryExtendedSize
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsDataTypeHandler::KsQueryExtendedSize method


## -description


The <b>KsQueryExtendedSize</b> method retrieves extended header information required for input and output (I/O) operations. 


## -syntax


````
HRESULT KsQueryExtendedSize(
  [out] ULONG *ExtendedSize
);
````


## -parameters




#### - ExtendedSize [out]

Pointer to a variable that receives the extended header size in bytes.


## -returns


Returns NOERROR if successful; otherwise, returns an error code.



## -remarks


If <b>KsQueryExtendedSize</b> returns zero at <i>ExtendedSize</i>, clients should not call the <a href="https://msdn.microsoft.com/16411d58-5fff-430f-b96d-78eed1dbb01c">KsPrepareIoOperation</a> and <a href="https://msdn.microsoft.com/46a58007-16bf-422b-8408-30a7b65dbee6">KsCompleteIoOperation</a> methods of the <a href="..\ksproxy\nn-ksproxy-iksdatatypehandler.md">IKsDataTypeHandler</a> interface because I/O preparation and completion operations are not required. For all other values that <b>KsQueryExtendedSize</b> returns at <i>ExtendedSize</i>, clients should allocate memory space for the extended stream header per the returned value and call <b>KsPrepareIoOperation</b> and <b>KsCompleteIoOperation</b> to prepare and complete the I/O operation associated with the header.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559831">IKsDataTypeHandler::KsPrepareIoOperation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559811">IKsDataTypeHandler::KsCompleteIoOperation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsDataTypeHandler::KsQueryExtendedSize method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

