---
UID: NF:filterpipeline.IFixedDocument.GetUri
title: IFixedDocument::GetUri method
author: windows-driver-content
description: The GetUri method gets the URI of the fixed document.
old-location: print\ifixeddocument_geturi.htm
old-project: print
ms.assetid: ed19deff-ecb3-4c6c-bbf5-a82a27b5934e
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IFixedDocument, IFixedDocument::GetUri, GetUri
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
req.alt-api: IFixedDocument.GetUri
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

# IFixedDocument::GetUri method



## -description
The <b>GetUri</b> method gets the URI of the fixed document.



## -syntax

````
HRESULT GetUri(
  [out] BSTR *uri
);
````


## -parameters

### -param uri [out]

The URI of the fixed document.


## -returns
<b>GetUri</b> returns an <b>HRESULT</b> value.


## -remarks
