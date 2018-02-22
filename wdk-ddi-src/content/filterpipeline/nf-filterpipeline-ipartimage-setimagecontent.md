---
UID: NF:filterpipeline.IPartImage.SetImageContent
title: IPartImage::SetImageContent method
author: windows-driver-content
description: The SetImageContent method sets an image property that is based on the content type.
old-location: print\ipartimage_setimagecontent.htm
old-project: print
ms.assetid: 5d7a59ac-93de-4a41-9313-df189e1f6e36
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: SetImageContent method [Print Devices], filterpipeline/IPartImage::SetImageContent, IPartImage, IPartImage::SetImageContent, SetImageContent method [Print Devices], IPartImage interface, IPartImage interface [Print Devices], SetImageContent method, SetImageContent, filterpipeline_1bbf6da0-f016-486d-a06d-768614fe1d5a.xml, print.ipartimage_setimagecontent
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
-	IPartImage.SetImageContent
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPartImage::SetImageContent method


## -description


The <b>SetImageContent</b> method sets an image property that is based on the content type.


## -syntax


````
HRESULT SetImageContent(
  [in] const wchar_t *contentType
);
````


## -parameters




### -param pContentType






#### - contentType [in]

The type of content of the image.


## -returns



<b>SetImageContent</b> returns an <b>HRESULT</b> value.



