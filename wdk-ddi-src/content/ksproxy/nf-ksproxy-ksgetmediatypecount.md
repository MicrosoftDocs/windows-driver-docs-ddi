---
UID: NF:ksproxy.KsGetMediaTypeCount
title: KsGetMediaTypeCount function
author: windows-driver-content
description: The KsGetMediaTypeCount function returns the number of available media types on a pin factory identifier.
old-location: stream\ksgetmediatypecount.htm
old-project: stream
ms.assetid: 157cb12c-1b2d-45b5-8541-e16ee3449064
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGetMediaTypeCount, KsGetMediaTypeCount function [Streaming Media Devices], ksproxy/KsGetMediaTypeCount, ksproxy_77c6249c-2b35-4d9e-afff-b01cf5518a73.xml, stream.ksgetmediatypecount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: Ksproxy.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ksproxy.lib
-	Ksproxy.dll
api_name:
-	KsGetMediaTypeCount
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# KsGetMediaTypeCount function


## -description


The <b>KsGetMediaTypeCount</b> function returns the number of available media types on a pin factory identifier.


## -syntax


````
HRESULT KsGetMediaTypeCount(
  _In_  HANDLE FilterHandle,
  _In_  ULONG  PinFactoryId,
  _Out_ ULONG  *MediaTypeCount
);
````


## -parameters




### -param FilterHandle [in]

Handle to the filter that contains the pin factory to query.


### -param PinFactoryId [in]

Identifier of the pin factory against which the number of media types is being returned.


### -param MediaTypeCount [out]

Pointer to a variable to receive the number of media types.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



The number of available media types that <b>KsGetMediaTypeCount</b> returns is equal to the number of available data ranges. 




## -see-also

<a href="..\ksproxy\nn-ksproxy-ikspinfactory.md">IKsPinFactory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a>



 

 


