---
UID: NF:filterpipeline.IPartImage.GetImageProperties
title: IPartImage::GetImageProperties method
author: windows-driver-content
description: The GetImageProperties method gets an image property that is based on the content type.
old-location: print\ipartimage_getimageproperties.htm
old-project: print
ms.assetid: 7ce333a3-86a2-47e5-b755-fd84469c8785
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPartImage, IPartImage::GetImageProperties, GetImageProperties
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
req.alt-api: IPartImage.GetImageProperties
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

# IPartImage::GetImageProperties method



## -description
The <b>GetImageProperties</b> method gets an image property that is based on the content type.



## -syntax

````
HRESULT GetImageProperties(
  [out] BSTR *pContentType
);
````


## -parameters

### -param pContentType [out]

The type of content for the image.


## -returns
<b>GetImageProperties</b> returns an <b>HRESULT</b> value.


## -remarks
