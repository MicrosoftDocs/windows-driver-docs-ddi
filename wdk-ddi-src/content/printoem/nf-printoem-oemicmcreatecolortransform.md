---
UID: NF:printoem.OEMIcmCreateColorTransform
title: OEMIcmCreateColorTransform function (printoem.h)
description: The OEMIcmCreateColorTransform function creates an ICM color transform.
tech.root: print
ms.date: 08/09/2022
keywords: ["OEMIcmCreateColorTransform function"]
ms.keywords: OEMIcmCreateColorTransform, OEMIcmCreateColorTransform function [Print Devices], print.oemicmcreatecolortransform, print_unidrv-pscript_rendering_102b853d-78f9-4e06-a3e5-c76f55caa42e.xml, printoem/OEMIcmCreateColorTransform
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
 - OEMIcmCreateColorTransform
 - printoem/OEMIcmCreateColorTransform
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMIcmCreateColorTransform
---

## -description

The **OEMIcmCreateColorTransform** function creates an ICM color transform.

## -parameters

### -param dhpdev

Defines the **DHPDEV** parameter *dhpdev*.

### -param pLogColorSpace

Defines the **LPLOGCOLORSPACEW** parameter *pLogColorSpace*.

### -param pvSourceProfile [in, optional]

Defines the **PVOID** parameter *pvSourceProfile*.

### -param cjSourceProfile

Defines the **ULONG** parameter *cjSourceProfile*.

### -param pvDestProfile [in]

Defines the **PVOID** parameter *pvDestProfile*.

### -param cjDestProfile

Defines the **ULONG** parameter *cjDestProfile*.

### -param pvTargetProfile [in, optional]

Defines the **PVOID** parameter *pvTargetProfile*.

### -param cjTargetProfile

Defines the **ULONG** parameter *cjTargetProfile*.

### -param dwReserved

Defines the **DWORD** parameter *dwReserved*.

## -returns

Returns a **HANDLE** value.
