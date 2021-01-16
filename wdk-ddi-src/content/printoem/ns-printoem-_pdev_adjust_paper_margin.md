---
UID: NS:printoem._PDEV_ADJUST_PAPER_MARGIN
title: _PDEV_ADJUST_PAPER_MARGIN (printoem.h)
description: The PDEV_ADJUST_PAPER_MARGIN structure specifies the imageable printing area.
old-location: print\pdev_adjust_paper_margin.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["PDEV_ADJUST_PAPER_MARGIN structure"]
ms.keywords: PDEV_ADJUST_PAPER_MARGIN, PDEV_ADJUST_PAPER_MARGIN structure [Print Devices], _PDEV_ADJUST_PAPER_MARGIN, print.pdev_adjust_paper_margin, print_unidrv-pscript_rendering_09d49312-b306-40c0-ad25-bc3669e8eedd.xml, printoem/PDEV_ADJUST_PAPER_MARGIN
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
req.typenames: PDEV_ADJUST_PAPER_MARGIN
f1_keywords:
 - _PDEV_ADJUST_PAPER_MARGIN
 - printoem/_PDEV_ADJUST_PAPER_MARGIN
 - PDEV_ADJUST_PAPER_MARGIN
 - printoem/PDEV_ADJUST_PAPER_MARGIN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _PDEV_ADJUST_PAPER_MARGIN
 - PDEV_ADJUST_PAPER_MARGIN
---

# _PDEV_ADJUST_PAPER_MARGIN structure


## -description

The PDEV_ADJUST_PAPER_MARGIN structure specifies the imageable printing area.

## -struct-fields

### -field rcImageableArea

Is a <a href="/windows/win32/api/windef/ns-windef-rectl">RECTL</a> structure that specifies the rectangular region that can be printed in. This region is specified in units of 0.001 mm.

## -remarks

This structure is available in Windows XP and later. 

The <i>pBuf</i> parameter of the <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps2-getpdevadjustment">IPrintOemPS2::GetPDEVAdjustment</a> method can point to a structure of this type.

## -see-also

<a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps2-getpdevadjustment">IPrintOemPS2::GetPDEVAdjustment</a>



<a href="/windows/win32/api/windef/ns-windef-rectl">RECTL</a>

