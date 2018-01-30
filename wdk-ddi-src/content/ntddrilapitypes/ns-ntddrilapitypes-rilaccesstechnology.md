---
UID: NS:ntddrilapitypes.RILACCESSTECHNOLOGY
title: RILACCESSTECHNOLOGY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilaccesstechnology.htm
old-project: netvista
ms.assetid: 28363041-4adc-4348-a1a5-2b9c11750286
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILACCESSTECHNOLOGY structure [Network Drivers Starting with Windows Vista], RILACCESSTECHNOLOGY, ntddrilapitypes/RILACCESSTECHNOLOGY, *LPRILACCESSTECHNOLOGY, netvista.rilaccesstechnology
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
-	RILACCESSTECHNOLOGY
product: Windows
targetos: Windows
req.typenames: "*LPRILACCESSTECHNOLOGY, RILACCESSTECHNOLOGY"
---

# RILACCESSTECHNOLOGY structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILACCESSTECHNOLOGY {
  DWORD                         cbSize;
  DWORD                         dwParams;
  DWORD                         dwSystemType;
  NULL                          RILACCESSTECHNOLOGYKINDUNION;
  RILACCESSTECHNOLOGYKINDUNION  kindUnion;
  RILEVDOKIND                   dwEvdoKind;
  RILGSMKIND                    dwGsmKind;
  RILUMTSKIND                   dwUmtsKind;
  RILTDSCDMAKIND                dwTdscdmaKind;
  RILLTEKIND                    dwLteKind;
} RILACCESSTECHNOLOGY, RILACCESSTECHNOLOGY;
````


## -struct-fields




### -field kindUnion



### -field kindUnion.dwEvdoKind

 


### -field kindUnion.dwGsmKind

 


### -field kindUnion.dwUmtsKind

 


### -field kindUnion.dwTdscdmaKind

 


### -field kindUnion.dwLteKind

 


### -field RILACCESSTECHNOLOGYKINDUNION



### -field cbSize



### -field dwParams



### -field dwSystemType



#### - dwEvdoKind



#### - dwGsmKind



#### - dwUmtsKind



#### - dwTdscdmaKind



#### - dwLteKind


