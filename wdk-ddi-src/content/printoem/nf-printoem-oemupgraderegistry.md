---
UID: NF:printoem.OEMUpgradeRegistry
title: OEMUpgradeRegistry function
author: windows-driver-content
description: OEMUpgradeRegistry function
old-location: print\oemupgraderegistry.htm
old-project: print
ms.assetid: 780ae330-907e-4e77-a5f9-cb44811f289f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMUpgradeRegistry, OEMUpgradeRegistry function [Print Devices], print.oemupgraderegistry, print_obsoletefunctions_5837e384-9879-4909-8dfa-f3c74486bde0.xml, printoem/OEMUpgradeRegistry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	printoem.h
api_name:
-	OEMUpgradeRegistry
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMUpgradeRegistry function


## -description




## -syntax


````
BOOL APIENTRY OEMUpgradeRegistry(
   DWORD                         dwLevel,
   PBYTE                         pDriverUpgradeInfo,
   PFN_DrvUpgradeRegistrySetting pfnUpgrade
);
````


## -parameters




### -param dwLevel


### -param pDriverUpgradeInfo


### -param pfnUpgrade


## -see-also

<a href="..\printoem\nc-printoem-pfn_drvupgraderegistrysetting.md">DrvUpgradeRegistrySetting</a>



 

 


