---
UID: NS:keyworddetectoroemadapter.__MIDL_IKeywordDetectorOemAdapter_0003
title: "__MIDL_IKeywordDetectorOemAdapter_0003"
author: windows-driver-content
description: The KEYWORDSELECTOR struct is a triplet of IDs that uniquely select a particular keyword, language, and user combination.
old-location: audio\keywordselector.htm
old-project: audio
ms.assetid: 762A7E36-E0F8-475C-B201-217D8FD8EBD6
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 0, 3, A, C, D, E, I, K, KEYWORDSELECTOR, KEYWORDSELECTOR structure [Audio Devices], L, M, O, R, S, T, W, Y, _, __MIDL_IKeywordDetectorOemAdapter_0003, a, audio.keywordselector, c, d, e, keyworddetectoroemadapter/KEYWORDSELECTOR, m, o, p, r, t, w, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: keyworddetectoroemadapter.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: KeywordDetectorOemAdapter.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	KeywordDetectorOemAdapter.h
apiname:
-	KEYWORDSELECTOR
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
---

# __MIDL_IKeywordDetectorOemAdapter_0003 structure


## -description


The <b>KEYWORDSELECTOR</b> struct is a triplet of IDs that uniquely select a particular keyword, language, and user combination.


## -syntax


````
typedef struct {
  KEYWORDID KeywordId;
  LANGID    LangId;
} KEYWORDSELECTOR;
````


## -struct-fields




### -field KeywordId

Identifies a keyword function.


### -field LangId

Identifies a language.

