---
UID: NS:ntnls._NLSTABLEINFO
title: "_NLSTABLEINFO"
author: windows-driver-content
description: Stores the NLS file formats .
old-location: kernel\nlstableinfo.htm
tech.root: kernel
ms.assetid: B9E64163-B338-49C9-8167-C36B110AB710
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PNLSTABLEINFO, NLSTABLEINFO, NLSTABLEINFO structure [Kernel-Mode Driver Architecture], PNLSTABLEINFO, PNLSTABLEINFO structure pointer [Kernel-Mode Driver Architecture], _NLSTABLEINFO, kernel.nlstableinfo, ntnls/NLSTABLEINFO, ntnls/PNLSTABLEINFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntnls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntnls.h
api_name:
-	NLSTABLEINFO
product:
- Windows
targetos: Windows
req.typenames: NLSTABLEINFO, *PNLSTABLEINFO
---

# _NLSTABLEINFO structure


## -description


Stores the NLS file formats .


## -struct-fields




### -field OemTableInfo

Specifies OEM table.


### -field AnsiTableInfo

Specifies an ANSI table. 


### -field UpperCaseTable

Specifies an 844 format uppercase table.


### -field LowerCaseTable

 




#### - PUSHORT

Specifies an 844 format lowercase table.

