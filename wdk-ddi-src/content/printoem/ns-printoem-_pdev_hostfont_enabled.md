---
UID: NS:printoem._PDEV_HOSTFONT_ENABLED
title: _PDEV_HOSTFONT_ENABLED (printoem.h)
description: The PDEV_HOSTFONT_ENABLED structure indicates whether the Hostfont feature is enabled.
old-location: print\pdev_hostfont_enabled.htm
tech.root: print
ms.assetid: f7fc7e33-e80b-449e-a1d1-a93740cd967c
ms.date: 04/20/2018
ms.keywords: PDEV_HOSTFONT_ENABLED, PDEV_HOSTFONT_ENABLED structure [Print Devices], _PDEV_HOSTFONT_ENABLED, print.pdev_hostfont_enabled, print_unidrv-pscript_rendering_81f0441f-4e35-493b-92a9-1836977f9c55.xml, printoem/PDEV_HOSTFONT_ENABLED
ms.topic: struct
req.header: printoem.h
req.include-header: Prcomoem.h
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
-	printoem.h
api_name:
-	PDEV_HOSTFONT_ENABLED
product:
- Windows
targetos: Windows
req.typenames: PDEV_HOSTFONT_ENABLED
---

# _PDEV_HOSTFONT_ENABLED structure


## -description


The PDEV_HOSTFONT_ENABLED structure indicates whether the Hostfont feature is enabled.


## -struct-fields




### -field bHostfontEnabled

Specifies whether the Hostfont feature is enabled. If set to <b>TRUE</b>, the Hostfont feature is enabled. Otherwise, this feature is disabled.


## -remarks



This structure is available in Windows XP and later. 

The <i>pBuf</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553189">IPrintOemPS2::GetPDEVAdjustment</a> method can point to a structure of this type.

Hostfont support is designed to improve the performance of a PostScript interpreter running on a host computer system, rather than on a physical printer. When the Hostfont feature is enabled, the Pscript5 driver stops converting and downloading host font data when there is already an identical font resident on the host on which the interpreter is running. This applies only to the following fonts:

<ul>
<li>
a TrueType Font (TTF) converted to either a PostScript Type 42 or CID2 font

</li>
<li>
an OpenType Font (OTF) converted to either a PostScript Type 1 or CID0 font

</li>
<li>
a Printer Font Binary (PFB)

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553189">IPrintOemPS2::GetPDEVAdjustment</a>
 

 

