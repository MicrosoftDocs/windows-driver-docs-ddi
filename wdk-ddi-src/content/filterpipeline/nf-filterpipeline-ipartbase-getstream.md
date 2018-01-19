---
UID: NF:filterpipeline.IPartBase.GetStream
title: IPartBase::GetStream method
author: windows-driver-content
description: The GetStream method gets the stream object that contains the part data. Each part has part-specific data that is associated with it (for example, a font, image, and page markup).
old-location: print\ipartbase_getstream.htm
old-project: print
ms.assetid: 83840bca-2e6e-4982-9ec1-e1e278908993
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPartBase, IPartBase::GetStream, GetStream
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
req.alt-api: IPartBase.GetStream
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

# IPartBase::GetStream method



## -description
The <b>GetStream</b> method gets the stream object that contains the part data. Each part has part-specific data that is associated with it (for example, a font, image, and page markup).



## -syntax

````
HRESULT GetStream(
  [out] IPrintReadStream **ppStream
);
````


## -parameters

### -param ppStream [out]

The stream object that contains the part data to be read.


## -returns
<b>GetStream</b> returns an <b>HRESULT</b> value.


## -remarks
