---
UID: NC:printoem.PFN_DrvUnidriverTextOut
title: PFN_DrvUnidriverTextOut (printoem.h)
description: The DrvUnidriverTextOut function is obsolete.
old-location: print\drvunidrivertextout.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["PFN_DrvUnidriverTextOut callback function"]
ms.keywords: PFN_DrvUnidriverTextOut, PFN_DrvUnidriverTextOut callback, PFN_DrvUnidriverTextOut callback function [Print Devices], print.drvunidrivertextout, print_obsoletefunctions_eeb13110-561c-4c0f-912b-1a3a1cebd846.xml, printoem/PFN_DrvUnidriverTextOut
req.header: printoem.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFN_DrvUnidriverTextOut
 - printoem/PFN_DrvUnidriverTextOut
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - printoem.h
api_name:
 - PFN_DrvUnidriverTextOut
---

# PFN_DrvUnidriverTextOut callback function


## -description

The <b>DrvUnidriverTextOut</b> function is obsolete.

Windows 2000 and later printer drivers should use <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvunitextout">IPrintOemDriverUni::DrvUniTextOut</a>. 

This function pointer prototype defines the type of the <b>DrvUnidriverTextOut</b> member of the <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_drvprocs">DRVPROCS</a> structure.

## -parameters

### -param pso

### -param pstro

### -param pfo

### -param pco

### -param prclExtra

### -param prclOpaque

### -param pboFore

### -param pboOpaque

### -param pptlBrushOrg

### -param mix
