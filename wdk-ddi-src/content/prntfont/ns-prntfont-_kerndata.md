---
UID: NS:prntfont._KERNDATA
title: "_KERNDATA"
author: windows-driver-content
description: The KERNDATA structure is used for describing printer kerning pairs.
old-location: print\kerndata.htm
tech.root: print
ms.assetid: b3f68c08-7097-46e7-ad47-6e5e1f2cb8b2
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: "*PKERNDATA, KERNDATA, KERNDATA structure [Print Devices], PKERNDATA, PKERNDATA structure pointer [Print Devices], _KERNDATA, print.kerndata, print_unidrv-pscript_fonts_9ddb2b69-839c-496a-b252-691570ee03cb.xml, prntfont/KERNDATA, prntfont/PKERNDATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: prntfont.h
req.include-header: Prntfont.h
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
-	prntfont.h
api_name:
-	KERNDATA
product:
- Windows
targetos: Windows
req.typenames: KERNDATA, *PKERNDATA
---

# _KERNDATA structure


## -description


The KERNDATA structure is used for describing printer kerning pairs.


## -struct-fields




### -field dwSize

Specifies the size, in bytes, of KERNDATA structure, including the <b>KernPair</b> array.


### -field dwKernPairNum

Specifies the number of elements in the <b>KernPair</b> array.


### -field KernPair

Is an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff565630">FD_KERNINGPAIR</a> structures.


## -remarks



A .ufm file's KERNDATA structures are accessed by a pointer in the file's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563587">UNIFM_HDR</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565630">FD_KERNINGPAIR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563587">UNIFM_HDR</a>
 

 

