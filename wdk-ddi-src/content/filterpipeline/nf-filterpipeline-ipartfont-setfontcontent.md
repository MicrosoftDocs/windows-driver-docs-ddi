---
UID: NF:filterpipeline.IPartFont.SetFontContent
title: IPartFont::SetFontContent method
author: windows-driver-content
description: The SetFontContent method sets the content of the font.
old-location: print\ipartfont_setfontcontent.htm
old-project: print
ms.assetid: bd77d32f-97fd-4f80-945d-9fff7553fcc5
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, C, F, I, IPartFont, IPartFont interface [Print Devices], SetFontContent method, IPartFont::SetFontContent, P, S, SetFontContent method [Print Devices], SetFontContent method [Print Devices], IPartFont interface, SetFontContent,IPartFont.SetFontContent, a, e, filterpipeline/IPartFont::SetFontContent, filterpipeline_1639cc2b-b1b6-4fa3-997b-3c98e32d2783.xml, n, o, print.ipartfont_setfontcontent, r, t"
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
-	IPartFont.SetFontContent
product: Windows
targetos: Windows
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




### -param pContentType






#### - contentType [in]

The type of the content for the font to be set.


## -returns



<b>SetFontContent</b> returns an <b>HRESULT</b> value.



