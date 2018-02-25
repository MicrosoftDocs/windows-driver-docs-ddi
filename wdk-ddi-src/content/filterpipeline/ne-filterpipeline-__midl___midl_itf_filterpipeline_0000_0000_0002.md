---
UID: NE:filterpipeline.__MIDL___MIDL_itf_filterpipeline_0000_0000_0002
title: "__MIDL___MIDL_itf_filterpipeline_0000_0000_0002"
author: windows-driver-content
description: The EXpsFontOptions enumeration describes the font options for an XPS part.
old-location: print\expsfontoptions.htm
old-project: print
ms.assetid: 3a92b219-91ee-4c11-b5c1-8e2e0cbff406
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 0, 2, D, E, EXpsFontOptions, EXpsFontOptions enumeration [Print Devices], F, Font_Normal, Font_Obfusticate, I, L, M, O, X, _, __MIDL___MIDL_itf_filterpipeline_0000_0000_0002, e, f, filterpipeline/EXpsFontOptions, filterpipeline/Font_Normal, filterpipeline/Font_Obfusticate, filterpipeline_252cd44a-7a00-40fb-9245-364c1453e2ef.xml, i, l, n, o, p, print.expsfontoptions, r, s, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
req.target-type: Windows
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	filterpipeline.h
apiname:
-	EXpsFontOptions
product: Windows
targetos: Windows
req.typenames: EXpsFontOptions
---

# __MIDL___MIDL_itf_filterpipeline_0000_0000_0002 enumeration


## -description


The EXpsFontOptions enumeration describes the font options for an XPS part.


## -syntax


````
typedef enum  { 
  Font_Normal,
  Font_Obfusticate
} EXpsFontOptions;
````


## -enum-fields




### -field Font_Normal

The font code is human-readable.


### -field Font_Obfusticate

The font code is obfusticated (that is, the internal structure of the font is scrambled in such a way to prevent someone from understaning how the structure works).

