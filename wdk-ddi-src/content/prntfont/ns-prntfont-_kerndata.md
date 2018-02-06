---
UID: NS:prntfont._KERNDATA
title: "_KERNDATA"
author: windows-driver-content
description: The KERNDATA structure is used for describing printer kerning pairs.
old-location: print\kerndata.htm
old-project: print
ms.assetid: b3f68c08-7097-46e7-ad47-6e5e1f2cb8b2
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: "_KERNDATA, print.kerndata, prntfont/KERNDATA, KERNDATA structure [Print Devices], KERNDATA, *PKERNDATA, print_unidrv-pscript_fonts_9ddb2b69-839c-496a-b252-691570ee03cb.xml, PKERNDATA, prntfont/PKERNDATA, PKERNDATA structure pointer [Print Devices]"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	prntfont.h
apiname:
-	KERNDATA
product: Windows
targetos: Windows
req.typenames: KERNDATA, *PKERNDATA
req.product: Windows 10 or later.
---

# _KERNDATA structure


## -description


The KERNDATA structure is used for describing printer kerning pairs.


## -syntax


````
typedef struct _KERNDATA {
  DWORD          dwSize;
  DWORD          dwKernPairNum;
  FD_KERNINGPAIR KernPair[1];
} KERNDATA, *PKERNDATA;
````


## -struct-fields




### -field dwSize

Specifies the size, in bytes, of KERNDATA structure, including the <b>KernPair</b> array.


### -field dwKernPairNum

Specifies the number of elements in the <b>KernPair</b> array.


### -field KernPair

Is an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff565630">FD_KERNINGPAIR</a> structures.


## -remarks


A .ufm file's KERNDATA structures are accessed by a pointer in the file's <a href="..\prntfont\ns-prntfont-_unifm_hdr.md">UNIFM_HDR</a> structure.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565630">FD_KERNINGPAIR</a>

<a href="..\prntfont\ns-prntfont-_unifm_hdr.md">UNIFM_HDR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20KERNDATA structure%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

