---
UID: NC:printoem.PFN_DrvUpdateUISetting
title: PFN_DrvUpdateUISetting (printoem.h)
description: The DrvUpdateUISetting function is obsolete.
tech.root: print
ms.date: 08/11/2022
keywords: ["PFN_DrvUpdateUISetting callback function"]
ms.keywords: DrvUpdateUISetting, DrvUpdateUISetting callback function [Print Devices], PFN_DrvUpdateUISetting, PFN_DrvUpdateUISetting callback, print.drvupdateuisetting, print_obsoletefunctions_8982b302-4efb-4a54-a3ae-a27c2dd0baa9.xml, printoem/DrvUpdateUISetting
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
 - PFN_DrvUpdateUISetting
---

## -description

The **DrvUpdateUISetting** function is obsolete.

 Windows 2000 and later UI plug-ins should use [IPrintOemDriverUI::DrvUpdateUISetting](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverui-drvupdateuisetting) or [IPrintCoreUI2::DrvUpdateUISetting](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcoreui2-drvupdateuisetting).

This function pointer prototype defines the type of the **DrvUpdateUISetting** member of the [OEMUIPROCS](/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiprocs) structure.

## -parameters

### -param pdriverobj

Defines the **PVOID** parameter *pdriverobj*.

### -param pOptItem

Defines the **PVOID** parameter *pOptItem*.

### -param dwPreviousSelection

Defines the **DWORD** parameter *dwPreviousSelection*.

### -param dwMode

Defines the **DWORD** parameter *dwMode*.

## -returns

Returns a **BOOL** value.
