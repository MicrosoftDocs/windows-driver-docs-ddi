---
UID: NF:printoem.OEMQueryDeviceSupport
title: OEMQueryDeviceSupport function (printoem.h)
description: The OEMQueryDeviceSupport function returns requested device-specific information.
tech.root: print
ms.date: 08/10/2022
keywords: ["OEMQueryDeviceSupport function"]
ms.keywords: OEMQueryDeviceSupport, OEMQueryDeviceSupport function [Print Devices], print.oemquerydevicesupport, print_unidrv-pscript_rendering_9bfec781-8785-4ff6-8abf-6e14233827dc.xml, printoem/OEMQueryDeviceSupport
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
 - OEMQueryDeviceSupport
 - printoem/OEMQueryDeviceSupport
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMQueryDeviceSupport
---

## -description

The **OEMQueryDeviceSupport** function returns requested device-specific information.

## -parameters

### -param pso

Defines the **SURFOBJ** parameter *pso*.

### -param pxlo

Defines the **XLATEOBJ** parameter *pxlo*.

### -param pxo

Defines the **XFORMOBJ** parameter *pxo*.

### -param iType

Defines the **ULONG** parameter *iType*.

### -param cjIn

Defines the **ULONG** parameter *cjIn*.

### -param pvIn [in]

Defines the **PVOID** parameter *pvIn*.

### -param cjOut

Defines the **ULONG** parameter *cjOut*.

### -param pvOut [out]

Defines the **PVOID** parameter *pvOut*.

## -returns

Returns a **BOOL** value.
