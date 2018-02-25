---
UID: NS:rilapitypes.RILMSGDCS
title: RILMSGDCS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgdcs_2.htm
old-project: netvista
ms.assetid: 50ef03af-3890-40dd-b0ed-7cf048f8530d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILMSGDCS, ,, C, D, G, I, L, M, P, R, RILMSGDCS, RILMSGDCS structure [Network Drivers Starting with Windows Vista], S, netvista.rilmsgdcs_2, rilapitypes/RILMSGDCS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
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
-	rilapitypes.h
apiname:
-	RILMSGDCS
product: Windows
targetos: Windows
req.typenames: RILMSGDCS, *LPRILMSGDCS
req.product: Windows 10 or later.
---

# RILMSGDCS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILMSGDCS {
  DWORD                cbSize;
  DWORD                dwParams;
  RILMSGDCSTYPE        dwType;
  DWORD                dwFlags;
  RILMSGDCSMSGCLASS    dwMsgClass;
  RILMSGDCSALPHABET    dwAlphabet;
  RILMSGDCSINDICATION  dwIndication;
  DWORD                dwLanguage;
} RILMSGDCS, RILMSGDCS;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwType


### -field dwFlags


### -field dwMsgClass


### -field dwAlphabet


### -field dwIndication


### -field dwLanguage

