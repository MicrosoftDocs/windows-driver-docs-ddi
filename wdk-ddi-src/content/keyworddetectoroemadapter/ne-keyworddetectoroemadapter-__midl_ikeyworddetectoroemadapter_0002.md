---
UID: NE:keyworddetectoroemadapter.__MIDL_IKeywordDetectorOemAdapter_0002
title: "__MIDL_IKeywordDetectorOemAdapter_0002"
author: windows-driver-content
description: The KEYWORDID enumeration identifies the phrase text/function of a keyword. The value is also be used in the Windows Biometric Service adapters.
old-location: audio\keywordid.htm
old-project: audio
ms.assetid: 88D85EB1-11BC-42B9-B22E-5FB58F409C75
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: KEYWORDID, KEYWORDID enumeration [Audio Devices], KwInvalid, KwSelection, KwVoiceAssistant, __MIDL_IKeywordDetectorOemAdapter_0002, audio.keywordid, keyworddetectoroemadapter/ KwSelection, keyworddetectoroemadapter/ KwVoiceAssistant, keyworddetectoroemadapter/KEYWORDID, keyworddetectoroemadapter/KwInvalid
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	KeywordDetectorOemAdapter.h
api_name:
-	KEYWORDID
product: Windows
targetos: Windows
req.typenames: KEYWORDID
---

# __MIDL_IKeywordDetectorOemAdapter_0002 enumeration


## -description


The <b>KEYWORDID</b> enumeration identifies the phrase text/function of a keyword. The value is also be used in the Windows Biometric Service adapters.


## -enum-fields




### -field KwInvalid

Indicates that the keyword was invalid.


### -field KwVoiceAssistant

Indicates that the "hey Cortana" keyword was used.


### -field KwSelection

Indicates the "select" keyword was used.

