---
UID: NS:wditypes._WDI_TYPE_MIC
title: "_WDI_TYPE_MIC"
author: windows-driver-content
description: The WDI_TYPE_MIC structure defines the MIC (802.11r).
old-location: netvista\wdi_type_mic.htm
old-project: netvista
ms.assetid: A21EEC35-98F2-4B68-A851-1C45D7F55194
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_WDI_TYPE_MIC, PWDI_TYPE_MIC, wditypes/PWDI_TYPE_MIC, WDI_TYPE_MIC structure [Network Drivers Starting with Windows Vista], *PWDI_TYPE_MIC, WDI_TYPE_MIC, PWDI_TYPE_MIC structure pointer [Network Drivers Starting with Windows Vista], netvista.wdi_type_mic, wditypes/WDI_TYPE_MIC"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wditypes.hpp
apiname:
-	WDI_TYPE_MIC
product: Windows
targetos: Windows
req.typenames: "*PWDI_TYPE_MIC, WDI_TYPE_MIC"
req.product: Windows 10 or later.
---

# _WDI_TYPE_MIC structure


## -description


The WDI_TYPE_MIC structure defines the MIC (802.11r).


## -syntax


````
typedef struct _WDI_TYPE_MIC {
  UINT8 Value[16];
} WDI_TYPE_MIC, *PWDI_TYPE_MIC;
````


## -struct-fields




### -field Value

The MIC.

