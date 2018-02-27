---
UID: NE:filterpipeline.__MIDL___MIDL_itf_filterpipeline_0000_0000_0004
title: "__MIDL___MIDL_itf_filterpipeline_0000_0000_0004"
author: windows-driver-content
description: "."
old-location: print\expsfontrestriction.htm
old-project: print
ms.assetid: 079BEF8A-514E-42C3-8916-95655C605098
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: EXpsFontRestriction, EXpsFontRestriction enumeration [Print Devices], Xps_Restricted_Font_Editable, Xps_Restricted_Font_Installable, Xps_Restricted_Font_NoEmbedding, Xps_Restricted_Font_PreviewPrint, __MIDL___MIDL_itf_filterpipeline_0000_0000_0004, filterpipeline/EXpsFontRestriction, filterpipeline/Xps_Restricted_Font_Editable, filterpipeline/Xps_Restricted_Font_Installable, filterpipeline/Xps_Restricted_Font_NoEmbedding, filterpipeline/Xps_Restricted_Font_PreviewPrint, print.expsfontrestriction
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: filterpipeline.h
req.include-header: 
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
-	Filterpipeline.h
apiname:
-	EXpsFontRestriction
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# __MIDL___MIDL_itf_filterpipeline_0000_0000_0004 enumeration


## -description





## -syntax


````
typedef enum __MIDL___MIDL_itf_filterpipeline_0000_0000_0004 { 
  Xps_Restricted_Font_Installable   = 0,
  Xps_Restricted_Font_NoEmbedding   = 0x2,
  Xps_Restricted_Font_PreviewPrint  = 0x4,
  Xps_Restricted_Font_Editable      = 0x8
} EXpsFontRestriction;
````


## -enum-fields




### -field Xps_Restricted_Font_Installable


### -field Xps_Restricted_Font_NoEmbedding


### -field Xps_Restricted_Font_PreviewPrint


### -field Xps_Restricted_Font_Editable

