---
UID: NF:filterpipeline.IPartBase.GetPartCompression
title: IPartBase::GetPartCompression method
author: windows-driver-content
description: The GetPartCompression method gets the compression of the part.
old-location: print\ipartbase_getpartcompression.htm
old-project: print
ms.assetid: 18b2a3c2-26da-434e-bcea-89bd6ef22077
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPartBase, IPartBase::GetPartCompression, GetPartCompression
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
req.alt-api: IPartBase.GetPartCompression
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

# IPartBase::GetPartCompression method



## -description
The <b>GetPartCompression</b> method gets the compression of the part.



## -syntax

````
HRESULT GetPartCompression(
  [out] EXpsCompressionOptions *pCompression
);
````


## -parameters

### -param pCompression [out]

A pointer to the compression option data for the part.


## -returns
<b>GetPartCompression</b> returns an <b>HRESULT</b> value.


## -remarks
