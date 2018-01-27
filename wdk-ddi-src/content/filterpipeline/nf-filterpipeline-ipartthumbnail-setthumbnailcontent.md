---
UID: NF:filterpipeline.IPartThumbnail.SetThumbnailContent
title: IPartThumbnail::SetThumbnailContent method
author: windows-driver-content
description: The SetThumbnailContent method sets the thumbnail content for the part.
old-location: print\ipartthumbnail_setthumbnailcontent.htm
old-project: print
ms.assetid: 7392aa0b-479a-473f-b8b5-34e14494e050
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: SetThumbnailContent, IPartThumbnail, filterpipeline_da595290-0b57-4b7d-a494-1f93b8f05470.xml, IPartThumbnail interface [Print Devices], SetThumbnailContent method, IPartThumbnail::SetThumbnailContent, print.ipartthumbnail_setthumbnailcontent, SetThumbnailContent method [Print Devices], filterpipeline/IPartThumbnail::SetThumbnailContent, SetThumbnailContent method [Print Devices], IPartThumbnail interface
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
-	IPartThumbnail.SetThumbnailContent
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPartThumbnail::SetThumbnailContent method


## -description


The <b>SetThumbnailContent</b> method sets the thumbnail content for the part.


## -syntax


````
HRESULT SetThumbnailContent(
  [in] const wchar_t *contentType
);
````


## -parameters




### -param pContentType





#### - contentType [in]

The type of content for the thumbnail.


## -returns


<b>SetThumbnailContent</b> returns an <b>HRESULT</b> value.


