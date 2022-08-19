---
UID: NS:printoem._PDEV_USE_TRUE_COLOR
title: PDEV_USE_TRUE_COLOR (printoem.h)
description: The PDEV_USE_TRUE_COLOR structure indicates whether the output color space should be color or grayscale.
tech.root: print
ms.date: 08/12/2022
keywords: ["PDEV_USE_TRUE_COLOR structure"]
ms.keywords: PDEV_USE_TRUE_COLOR, PDEV_USE_TRUE_COLOR structure [Print Devices], _PDEV_USE_TRUE_COLOR, print.pdev_use_true_color, print_unidrv-pscript_rendering_bac188d1-ddd5-44e6-b2f1-7c617d6c4b6f.xml, printoem/PDEV_USE_TRUE_COLOR
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
targetos: Windows
req.typenames: PDEV_USE_TRUE_COLOR
f1_keywords:
 - _PDEV_USE_TRUE_COLOR
 - printoem/_PDEV_USE_TRUE_COLOR
 - PDEV_USE_TRUE_COLOR
 - printoem/PDEV_USE_TRUE_COLOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _PDEV_USE_TRUE_COLOR
 - PDEV_USE_TRUE_COLOR
---

## -description

The **PDEV_USE_TRUE_COLOR** structure indicates whether the output color space should be color or grayscale.

## -struct-fields

### -field bUseTrueColor

Specifies whether the PostScript output should be in color mode or in monochrome/grayscale mode. If **TRUE**, output is in color. If **FALSE**, output is monochrome/grayscale.

## -remarks

This structure is available in Windows XP and later.

The *pBuf* parameter of the [IPrintOemPS2::GetPDEVAdjustment](../prcomoem/nf-prcomoem-iprintoemps2-getpdevadjustment.md) method can point to a structure of this type.

A plug-in can use this flag to turn color output on or off for Pscript5 printer output data. If the plug-in chooses to not change the current setting, it can simply return **S_FALSE**.

## -see-also

[IPrintOemPS2::GetPDEVAdjustment](../prcomoem/nf-prcomoem-iprintoemps2-getpdevadjustment.md)