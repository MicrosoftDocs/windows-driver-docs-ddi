---
UID: NF:filterpipeline.IPartFont.SetFontOptions
title: IPartFont::SetFontOptions method
author: windows-driver-content
description: The SetFontOptions method sets the options for the font.
old-location: print\ipartfont_setfontoptions.htm
old-project: print
ms.assetid: 28c708b7-82bb-4246-bde8-88d471c8120c
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: SetFontOptions method [Print Devices], IPartFont interface, SetFontOptions, filterpipeline/IPartFont::SetFontOptions, filterpipeline_9461a7cc-ee59-4710-ada4-ebea899babaa.xml, IPartFont::SetFontOptions, print.ipartfont_setfontoptions, SetFontOptions method [Print Devices], IPartFont, IPartFont interface [Print Devices], SetFontOptions method
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
-	IPartFont.SetFontOptions
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPartFont::SetFontOptions method


## -description


The <b>SetFontOptions</b> method sets the options for the font.


## -syntax


````
HRESULT SetFontOptions(
  [in] EXpsFontOptions options
);
````


## -parameters




### -param options [in]

An <a href="..\filterpipeline\ne-filterpipeline-__midl___midl_itf_filterpipeline_0000_0000_0002.md">ExpsFontOptions</a>-typed value that describes the options for the font.


## -returns


<b>SetFontOptions</b> returns an <b>HRESULT</b> value.


