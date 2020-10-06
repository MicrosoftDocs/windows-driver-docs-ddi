---
UID: NC:printoem.PFN_DrvUpdateUISetting
title: PFN_DrvUpdateUISetting (printoem.h)
description: The DrvUpdateUISetting function is obsolete.
old-location: print\drvupdateuisetting.htm
tech.root: print
ms.assetid: 37f8ab73-ff81-4150-b1f6-faec5ca76908
ms.date: 04/20/2018
keywords: ["PFN_DrvUpdateUISetting callback function"]
ms.keywords: DrvUpdateUISetting, DrvUpdateUISetting callback function [Print Devices], PFN_DrvUpdateUISetting, PFN_DrvUpdateUISetting callback, print.drvupdateuisetting, print_obsoletefunctions_8982b302-4efb-4a54-a3ae-a27c2dd0baa9.xml, printoem/DrvUpdateUISetting
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
 - PFN_DrvUpdateUISetting
 - printoem/PFN_DrvUpdateUISetting
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - printoem.h
api_name:
 - DrvUpdateUISetting
---

# PFN_DrvUpdateUISetting callback function


## -description

The <b>DrvUpdateUISetting</b> function is obsolete.

 Windows 2000 and later UI plug-ins should use <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverui-drvupdateuisetting">IPrintOemDriverUI::DrvUpdateUISetting</a> or <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcoreui2-drvupdateuisetting">IPrintCoreUI2::DrvUpdateUISetting</a>. 

This function pointer prototype defines the type of the <b>DrvUpdateUISetting</b> member of the <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiprocs">OEMUIPROCS</a> structure.

## -parameters

### -param pdriverobj

### -param pOptItem

### -param dwPreviousSelection

### -param dwMode