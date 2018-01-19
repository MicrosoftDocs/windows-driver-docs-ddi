---
UID: NF:filterpipeline.IPartFont.SetFontContent
title: IPartFont::SetFontContent method
author: windows-driver-content
description: The SetFontContent method sets the content of the font.
old-location: print\ipartfont_setfontcontent.htm
old-project: print
ms.assetid: bd77d32f-97fd-4f80-945d-9fff7553fcc5
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPartFont, IPartFont::SetFontContent, SetFontContent
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
req.alt-api: IPartFont.SetFontContent
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

# IPartFont::SetFontContent method



## -description
The <b>SetFontContent</b> method sets the content of the font.



## -syntax

````
HRESULT SetFontContent(
  [in] const wchar_t *contentType
);
````


## -parameters

### -param contentType [in]

The type of the content for the font to be set.


## -returns
<b>SetFontContent</b> returns an <b>HRESULT</b> value.


## -remarks
