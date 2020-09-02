---
UID: NC:printoem.PFN_DrvUpgradeRegistrySetting
title: PFN_DrvUpgradeRegistrySetting (printoem.h)
description: The DrvUpgradeRegistrySetting function is obsolete.
old-location: print\drvupgraderegistrysetting.htm
tech.root: print
ms.assetid: cb03b9d4-b623-49b8-a63d-ae97b33065c5
ms.date: 04/20/2018
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
 - DrvUpgradeRegistrySetting
---

# PFN_DrvUpgradeRegistrySetting callback function


## -description

The <b>DrvUpgradeRegistrySetting</b> function is obsolete.

 Windows 2000 and later UI plug-ins should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverui-drvupgraderegistrysetting">IPrintOemDriverUI::DrvUpgradeRegistrySetting</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcoreui2-drvupgraderegistrysetting">IPrintCoreUI2::DrvUpgradeRegistrySetting</a>.

This function pointer prototype defines the type of the <i>pfnUpgrade</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nf-printoem-oemupgraderegistry">OEMUpgradeRegistry</a> function.

## -parameters

### -param hPrinter

### -param pFeature

### -param pOption

