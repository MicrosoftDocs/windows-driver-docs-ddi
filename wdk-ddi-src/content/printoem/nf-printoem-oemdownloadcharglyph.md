---
UID: NF:printoem.OEMDownloadCharGlyph
title: OEMDownloadCharGlyph function
author: windows-driver-content
description: OEMDownloadCharGlyph function
old-location: print\oemdownloadcharglyph.htm
old-project: print
ms.assetid: da9a4058-1a0e-484b-afcd-9d4558810acd
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , C, D, E, G, M, O, OEMDownloadCharGlyph, OEMDownloadCharGlyph function [Print Devices], a, d, h, l, n, o, p, print.oemdownloadcharglyph, print_obsoletefunctions_fb2af04d-799c-419c-b675-3444fd7d3143.xml, printoem/OEMDownloadCharGlyph, r, w, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	OEMDownloadCharGlyph
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMDownloadCharGlyph function


## -description




## -syntax


````
DWORD APIENTRY OEMDownloadCharGlyph(
        PDEVOBJ     pdevobj,
        PUNIFONTOBJ pUFObj,
        HGLYPH      hGlyph,
  _Out_ PDWORD      pdwWidth
);
````


## -parameters




### -param pdevobj


### -param pUFObj


### -param hGlyph


### -param pdwWidth [out]

