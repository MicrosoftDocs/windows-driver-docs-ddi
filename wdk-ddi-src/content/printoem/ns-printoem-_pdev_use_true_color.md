---
UID: NS:printoem._PDEV_USE_TRUE_COLOR
title: "_PDEV_USE_TRUE_COLOR"
author: windows-driver-content
description: The PDEV_USE_TRUE_COLOR structure indicates whether the output color space should be color or grayscale.
old-location: print\pdev_use_true_color.htm
old-project: print
ms.assetid: 75ffe04a-4d77-4486-8fc7-35b0b6144b99
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PDEV_USE_TRUE_COLOR, _PDEV_USE_TRUE_COLOR, PDEV_USE_TRUE_COLOR structure [Print Devices], print_unidrv-pscript_rendering_bac188d1-ddd5-44e6-b2f1-7c617d6c4b6f.xml, printoem/PDEV_USE_TRUE_COLOR, print.pdev_use_true_color
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	PDEV_USE_TRUE_COLOR
product: Windows
targetos: Windows
req.typenames: PDEV_USE_TRUE_COLOR
req.product: Windows 10 or later.
---

# _PDEV_USE_TRUE_COLOR structure


## -description


The PDEV_USE_TRUE_COLOR structure indicates whether the output color space should be color or grayscale.


## -syntax


````
typedef struct _PDEV_USE_TRUE_COLOR {
  BOOL bUseTrueColor;
} PDEV_USE_TRUE_COLOR;
````


## -struct-fields




### -field bUseTrueColor

Specifies whether the PostScript output should be in color mode or in monochrome/grayscale mode. If <b>TRUE</b>, output is in color. If <b>FALSE</b>, output is monochrome/grayscale.


## -remarks


This structure is available in Windows XP and later. 

The <i>pBuf</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553189">IPrintOemPS2::GetPDEVAdjustment</a> method can point to a structure of this type.

A plug-in can use this flag to turn color output on or off for Pscript5 printer output data. If the plug-in chooses to not change the current setting, it can simply return S_FALSE.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553189">IPrintOemPS2::GetPDEVAdjustment</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20PDEV_USE_TRUE_COLOR structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

