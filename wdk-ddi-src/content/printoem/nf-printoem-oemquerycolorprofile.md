---
UID: NF:printoem.OEMQueryColorProfile
title: OEMQueryColorProfile function (printoem.h)
description: Describes the OEMQueryColorProfile function.
tech.root: print
ms.date: 08/10/2022
keywords: ["OEMQueryColorProfile function"]
ms.keywords: OEMQueryColorProfile, OEMQueryColorProfile function [Print Devices], print.oemquerycolorprofile, print_obsoletefunctions_f21cf62d-45bd-4248-8b0c-a19cc982ad3c.xml, printoem/OEMQueryColorProfile
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
 - OEMQueryColorProfile
 - printoem/OEMQueryColorProfile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMQueryColorProfile
---

## -description

Describes the **OEMQueryColorProfile** function.

## -parameters

### -param hPrinter

Defines the **HANDLE** parameter *hPrinter*.

### -param poemuiobj

Defines the **POEMUIOBJ** parameter *poemuiobj*.

### -param pPublicDM

Defines the **PDEVMODE** parameter *pPublicDM*.

### -param pOEMDM

Defines the **PVOID** parameter *pOEMDM*.

### -param ulQueryMode

Defines the **ULONG** parameter *ulQueryMode*.

### -param pvProfileData [out]

Defines the **VOID** parameter *pvProfileData*.

### -param pcbProfileData [out]

Defines the **ULONG** parameter *pcbProfileData*.

### -param pflProfileData [out]

Defines the **FLONG** parameter *pflProfileData*.

## -returns

Returns a **BOOL** value.
