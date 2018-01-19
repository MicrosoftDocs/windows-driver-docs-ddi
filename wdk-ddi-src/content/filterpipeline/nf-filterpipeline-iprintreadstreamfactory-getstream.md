---
UID: NF:filterpipeline.IPrintReadStreamFactory.GetStream
title: IPrintReadStreamFactory::GetStream method
author: windows-driver-content
description: The GetStream method gets the stream interface.
old-location: print\iprintreadstreamfactory_getstream.htm
old-project: print
ms.assetid: 47447f00-a57d-4821-b10e-1b2cf7eaad94
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintReadStreamFactory, IPrintReadStreamFactory::GetStream, GetStream
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
req.alt-api: IPrintReadStreamFactory.GetStream
req.alt-loc: filterpipeline.h
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

# IPrintReadStreamFactory::GetStream method



## -description
The <code>GetStream</code> method gets the stream interface.



## -syntax

````
HRESULT GetStream(
  [out] IPrintReadStream **ppStream
);
````


## -parameters

### -param ppStream [out]

A pointer to an <a href="..\filterpipeline\nn-filterpipeline-iprintreadstream.md">IPrintReadStream</a> interface. The filter can use this interface to read the contents of the print ticket.


## -returns
<code>GetStream</code> returns an <b>HRESULT</b> value.


## -remarks
The following code example shows how a filter can use <b>IPrintReadStreamFactory</b> to access the per-user print ticket.</p>