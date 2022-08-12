---
UID: NC:printoem.PFN_DrvUpgradeRegistrySetting
title: PFN_DrvUpgradeRegistrySetting (printoem.h)
description: The DrvUpgradeRegistrySetting function is obsolete.
tech.root: print
ms.date: 08/11/2022
keywords: ["PFN_DrvUpgradeRegistrySetting callback function"]
ms.keywords: DrvUpgradeRegistrySetting, DrvUpgradeRegistrySetting callback function [Print Devices], PFN_DrvUpgradeRegistrySetting, PFN_DrvUpgradeRegistrySetting callback, print.drvupgraderegistrysetting, print_obsoletefunctions_089531d9-0bcb-4fed-84c4-59a3be1ed82e.xml, printoem/DrvUpgradeRegistrySetting
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
 - PFN_DrvUpgradeRegistrySetting
 - printoem/PFN_DrvUpgradeRegistrySetting
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - printoem.h
api_name:
 - PFN_DrvUpgradeRegistrySetting
---

## -description

The **DrvUpgradeRegistrySetting** function is obsolete.

 Windows 2000 and later UI plug-ins should use [IPrintOemDriverUI::DrvUpgradeRegistrySetting](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverui-drvupgraderegistrysetting) or [IPrintCoreUI2::DrvUpgradeRegistrySetting](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcoreui2-drvupgraderegistrysetting).

This function pointer prototype defines the type of the *pfnUpgrade* parameter of the [OEMUpgradeRegistry](/windows-hardware/drivers/ddi/printoem/nf-printoem-oemupgraderegistry) function.

## -parameters

### -param hPrinter

Defines the **HANDLE** parameter *hPrinter*.

### -param pFeature

Defines the **PCSTR** parameter *pFeature*.

### -param pOption

Defines the **PCSTR** parameter *pOption*.

## -returns

Returns a **BOOL** value.
