---
UID: NS:printoem._PDEV_HOSTFONT_ENABLED
title: PDEV_HOSTFONT_ENABLED (printoem.h)
description: The PDEV_HOSTFONT_ENABLED structure indicates whether the Hostfont feature is enabled.
tech.root: print
ms.date: 08/12/2022
keywords: ["PDEV_HOSTFONT_ENABLED structure"]
ms.keywords: PDEV_HOSTFONT_ENABLED, PDEV_HOSTFONT_ENABLED structure [Print Devices], _PDEV_HOSTFONT_ENABLED, print.pdev_hostfont_enabled, print_unidrv-pscript_rendering_81f0441f-4e35-493b-92a9-1836977f9c55.xml, printoem/PDEV_HOSTFONT_ENABLED
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
req.typenames: PDEV_HOSTFONT_ENABLED
f1_keywords:
 - _PDEV_HOSTFONT_ENABLED
 - printoem/_PDEV_HOSTFONT_ENABLED
 - PDEV_HOSTFONT_ENABLED
 - printoem/PDEV_HOSTFONT_ENABLED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _PDEV_HOSTFONT_ENABLED
 - PDEV_HOSTFONT_ENABLED
---

## -description

The **PDEV_HOSTFONT_ENABLED** structure indicates whether the Hostfont feature is enabled.

## -struct-fields

### -field bHostfontEnabled

Specifies whether the Hostfont feature is enabled. If set to **TRUE**, the Hostfont feature is enabled. Otherwise, this feature is disabled.

## -remarks

This structure is available in Windows XP and later.

The *pBuf* parameter of the [IPrintOemPS2::GetPDEVAdjustment](../prcomoem/nf-prcomoem-iprintoemps2-getpdevadjustment.md) method can point to a structure of this type.

Hostfont support is designed to improve the performance of a PostScript interpreter running on a host computer system, rather than on a physical printer. When the Hostfont feature is enabled, the Pscript5 driver stops converting and downloading host font data when there is already an identical font resident on the host on which the interpreter is running. This applies only to the following fonts:

- A TrueType Font (TTF) converted to either a PostScript Type 42 or CID2 font

- An OpenType Font (OTF) converted to either a PostScript Type 1 or CID0 font

- A Printer Font Binary (PFB)

## -see-also

[IPrintOemPS2::GetPDEVAdjustment](../prcomoem/nf-prcomoem-iprintoemps2-getpdevadjustment.md)