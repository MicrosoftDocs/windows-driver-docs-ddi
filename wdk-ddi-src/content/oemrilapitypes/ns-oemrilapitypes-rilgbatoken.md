---
UID: NS:oemrilapitypes.RILGBATOKEN
title: RILGBATOKEN
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgbatoken.htm
old-project: netvista
ms.assetid: f842d945-1d1e-4f0b-9cc9-82a8401c170a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILGBATOKEN structure [Network Drivers Starting with Windows Vista], oemrilapitypes/RILGBATOKEN, oemrilapitypes/LPRILGBATOKEN, LPRILGBATOKEN structure pointer [Network Drivers Starting with Windows Vista], RILGBATOKEN, netvista.rilgbatoken, *LPRILGBATOKEN, LPRILGBATOKEN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: oemrilapitypes.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	oemrilapitypes.h
apiname:
-	RILGBATOKEN
product: Windows
targetos: Windows
req.typenames: "*LPRILGBATOKEN, RILGBATOKEN"
---

# RILGBATOKEN structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILGBATOKEN {
  DWORD   cbSize;
  DWORD   cbBTIDSize;
  DWORD   dwBTIDOffset;
  DWORD   cbNAFKeyLifetimeSize;
  DWORD   dwNAFKeyLifetimeOffset;
  DWORD   cbNAFKeySize;
  DWORD   dwNAFKeyOffset;
  BYTE [] bData;
} RILGBATOKEN, *LPRILGBATOKEN;
````


## -struct-fields




### -field cbSize


### -field cbBTIDSize


### -field dwBTIDOffset


### -field cbNAFKeyLifetimeSize


### -field dwNAFKeyLifetimeOffset


### -field cbNAFKeySize


### -field dwNAFKeyOffset


### -field bData

