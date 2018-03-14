---
UID: NF:printoem.OEMDevQueryPrintEx
title: OEMDevQueryPrintEx function
author: windows-driver-content
description: OEMDevQueryPrintEx function
old-location: print\oemdevqueryprintex.htm
old-project: print
ms.assetid: 3d555be3-2a1b-40b4-adf4-b797bb4b09b7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMDevQueryPrintEx, OEMDevQueryPrintEx function [Print Devices], print.oemdevqueryprintex, print_obsoletefunctions_c58c63fe-eeae-444d-a0e2-df17b61fa1ed.xml, printoem/OEMDevQueryPrintEx
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
-	OEMDevQueryPrintEx
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMDevQueryPrintEx function


## -description




## -syntax


````
BOOL APIENTRY OEMDevQueryPrintEx(
   POEMUIOBJ           poemuiobj,
   PDEVQUERYPRINT_INFO pDQPInfo,
   PDEVMODE            pPublicDM,
   PVOID               pOEMDM
);
````


## -parameters




### -param poemuiobj


### -param pDQPInfo


### -param pPublicDM


### -param pOEMDM

