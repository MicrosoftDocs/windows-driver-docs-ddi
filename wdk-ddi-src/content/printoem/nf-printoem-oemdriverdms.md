---
UID: NF:printoem.OEMDriverDMS
title: OEMDriverDMS function
author: windows-driver-content
description: OEMDriverDMS function
old-location: print\oemdriverdms.htm
old-project: print
ms.assetid: 261d4dbc-6374-4b11-80a0-64b0a2fc6abe
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print_obsoletefunctions_2ae5b734-4f6d-4d91-baba-b594a3388d08.xml, printoem/OEMDriverDMS, OEMDriverDMS, print.oemdriverdms, OEMDriverDMS function [Print Devices]
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	OEMDriverDMS
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMDriverDMS function


## -description




## -syntax


````
BOOL APIENTRY OEMDriverDMS(
        PVOID                        pDevObj,
  _Out_ _writes_bytes_(cbSize) PVOID pBuffer,
        DWORD                        cbSize,
  _Out_ PDWORD                       pcbNeeded
);
````


## -parameters




### -param pDevObj



### -param pBuffer [out]



### -param cbSize



### -param pcbNeeded [out]


