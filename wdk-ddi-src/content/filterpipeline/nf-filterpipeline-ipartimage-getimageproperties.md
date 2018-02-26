---
UID: NF:filterpipeline.IPartImage.GetImageProperties
title: IPartImage::GetImageProperties method
author: windows-driver-content
description: The GetImageProperties method gets an image property that is based on the content type.
old-location: print\ipartimage_getimageproperties.htm
old-project: print
ms.assetid: 7ce333a3-86a2-47e5-b755-fd84469c8785
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, G, GetImageProperties method [Print Devices], GetImageProperties method [Print Devices], IPartImage interface, GetImageProperties,IPartImage.GetImageProperties, I, IPartImage, IPartImage interface [Print Devices], GetImageProperties method, IPartImage::GetImageProperties, P, a, e, filterpipeline/IPartImage::GetImageProperties, filterpipeline_06d3e014-e30a-44d2-a6e0-769cb62c387d.xml, g, i, m, o, p, print.ipartimage_getimageproperties, r, s, t"
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: filterpipeline.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	filterpipeline.h
apiname:
-	IPartImage.GetImageProperties
product: Windows
targetos: Windows
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



