---
UID: NF:printoem.OEMUpgradeRegistry
title: OEMUpgradeRegistry function (printoem.h)
description: Describes the OEMUpgradeRegistry function.
tech.root: print
ms.date: 08/11/2022
keywords: ["OEMUpgradeRegistry function"]
ms.keywords: OEMUpgradeRegistry, OEMUpgradeRegistry function [Print Devices], print.oemupgraderegistry, print_obsoletefunctions_5837e384-9879-4909-8dfa-f3c74486bde0.xml, printoem/OEMUpgradeRegistry
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
 - OEMUpgradeRegistry
 - printoem/OEMUpgradeRegistry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMUpgradeRegistry
---

## -description

Describes the **OEMUpgradeRegistry** function.

## -parameters

### -param dwLevel

Defines the **DWORD** parameter *dwLevel*.

### -param pDriverUpgradeInfo

Defines the **PBYTE** parameter *pDriverUpgradeInfo*.

### -param pfnUpgrade

Defines the **PFN_DrvUpgradeRegistrySetting** parameter *pfnUpgrade*.

## -returns

Returns a **BOOL** value.

## -see-also

[DrvUpgradeRegistrySetting](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvupgraderegistrysetting)
