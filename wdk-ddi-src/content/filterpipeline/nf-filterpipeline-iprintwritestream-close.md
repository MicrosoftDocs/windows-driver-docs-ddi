---
UID: NF:filterpipeline.IPrintWriteStream.Close
title: IPrintWriteStream::Close method
author: windows-driver-content
description: The Close method closes a stream and ends the writing to that stream. This method is mandatory. You must call this method when the filter is done writing.
old-location: print\iprintwritestream_close.htm
old-project: print
ms.assetid: d3f828bf-854f-4d2d-a869-ee5c002a1728
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintWriteStream, IPrintWriteStream::Close, Close
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintWriteStream.Close
req.alt-loc: Filterpipeline.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: EXpsFontRestriction
---

# IPrintWriteStream::Close method



## -description
The <code>Close</code> method closes a stream and ends the writing to that stream. This method is mandatory. You must call this method when the filter is done writing.



## -syntax

````
void STDMETHODCALLTYPE Close(
    None
);
````


## -parameters

### -param None 


## -returns
None


## -remarks
