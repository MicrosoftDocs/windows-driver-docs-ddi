---
UID: NF:ksproxy.IKsDataTypeHandler.KsIsMediaTypeInRanges
title: IKsDataTypeHandler::KsIsMediaTypeInRanges method
author: windows-driver-content
description: The KsIsMediaTypeInRanges method validates that a media type is within the provided data ranges.
old-location: stream\iksdatatypehandler_ksismediatypeinranges.htm
old-project: stream
ms.assetid: 354dcd2b-fa63-4574-94d8-149e3f199751
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsIsMediaTypeInRanges method [Streaming Media Devices], IKsDataTypeHandler interface, IKsDataTypeHandler, ksproxy/IKsDataTypeHandler::KsIsMediaTypeInRanges, KsIsMediaTypeInRanges method [Streaming Media Devices], ksproxy_ebd4f24e-02a2-4228-b11b-890693ece498.xml, IKsDataTypeHandler::KsIsMediaTypeInRanges, IKsDataTypeHandler interface [Streaming Media Devices], KsIsMediaTypeInRanges method, KsIsMediaTypeInRanges, stream.iksdatatypehandler_ksismediatypeinranges
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: 
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
-	IKsDataTypeHandler.KsIsMediaTypeInRanges
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsDataTypeHandler::KsIsMediaTypeInRanges method


## -description


The <b>KsIsMediaTypeInRanges</b> method validates that a media type is within the provided data ranges.


## -syntax


````
HRESULT KsIsMediaTypeInRanges(
  [in] PVOID DataRanges
);
````


## -parameters




### -param DataRanges [in]

Pointer to a buffer that contains a <a href="..\ks\ns-ks-ksmultiple_item.md">KSMULTIPLE_ITEM</a> structure, followed by a sequence of extensible <a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a> structures, aligned on 64-bit boundaries. The KSMULTIPLE_ITEM structure is a header that describes the size of the buffer and the number of entries in the list that follows the header.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



A client first calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559844">IKsDataTypeHandler::KsSetMediaType</a> method to assign a media type that the client references in subsequent operations on the data type handler. The client then calls <b>KsIsMediaTypeInRanges</b> to validate that the media type is within particular data ranges. 




## -see-also

<a href="..\ks\ns-ks-ksmultiple_item.md">KSMULTIPLE_ITEM</a>



<a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559844">IKsDataTypeHandler::KsSetMediaType</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsDataTypeHandler::KsIsMediaTypeInRanges method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

