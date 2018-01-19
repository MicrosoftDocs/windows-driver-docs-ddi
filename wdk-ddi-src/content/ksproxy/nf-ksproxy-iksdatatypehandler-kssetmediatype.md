---
UID: NF:ksproxy.IKsDataTypeHandler.KsSetMediaType
title: IKsDataTypeHandler::KsSetMediaType method
author: windows-driver-content
description: The KsSetMediaType method sets the media type for a data type handler.
old-location: stream\iksdatatypehandler_kssetmediatype.htm
old-project: stream
ms.assetid: b1c97d4f-b305-4c9f-b3fd-06d0ebcb0ed0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsDataTypeHandler, IKsDataTypeHandler::KsSetMediaType, KsSetMediaType
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
req.alt-api: IKsDataTypeHandler.KsSetMediaType
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

# IKsDataTypeHandler::KsSetMediaType method



## -description
The <b>KsSetMediaType</b> method sets the media type for a data type handler. 



## -syntax

````
HRESULT KsSetMediaType(
  [in] const AM_MEDIA_TYPE *MediaType
);
````


## -parameters

### -param MediaType [in]

Pointer to a <b>CMediaType</b> object associated with the media type.


## -returns
Returns NOERROR if successful; otherwise, returns an error code.


## -remarks
Clients can call <b>KsSetMediaType</b> of a single data type handler to initialize this data type handler to a particular media type from a group of many disparate media types.

For more information about <b>CMediaType</b> class, see the Microsoft Windows SDK documentation.


## -see-also
<dl>
<dt>
<a href="..\ksproxy\nn-ksproxy-iksdatatypehandler.md">IKsDataTypeHandler</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsDataTypeHandler::KsSetMediaType method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

