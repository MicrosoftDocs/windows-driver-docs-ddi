---
UID: NF:printoem.OEMPaint
title: OEMPaint function (printoem.h)
description: The OEMPaint function is obsolete, and is no longer called by GDI in Windows 2000 and later. See DrvPaint.
old-location: print\oempaint.htm
tech.root: print
ms.assetid: 4054c805-5307-41f4-a7ff-65743ae4be69
ms.date: 04/20/2018
keywords: ["OEMPaint function"]
ms.keywords: OEMPaint, OEMPaint function [Print Devices], print.oempaint, print_unidrv-pscript_rendering_c9624a47-02fd-4eba-80d9-4035713ac594.xml, printoem/OEMPaint
f1_keywords:
 - "printoem/OEMPaint"
 - "OEMPaint"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- printoem.h
api_name:
- OEMPaint
targetos: Windows
req.typenames: 
---

# OEMPaint function


## -description


The <code>OEMPaint</code> function is obsolete, and is no longer called by GDI in Windows 2000 and later. See <a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvpaint">DrvPaint</a>.


## -parameters




### -param pso


### -param pco


### -param pbo


### -param pptlBrushOrg


### -param mix


## -remarks



If you call into the core driver, cast the call using the <b>PFN_DrvPaint</b> function pointer.



