---
UID: NS:ntddrilapitypes.RILUICCAPPINFO
title: RILUICCAPPINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccappinfo.htm
old-project: netvista
ms.assetid: b3a688fe-928c-458e-ac47-59a9ae61bc5e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILUICCAPPINFO, ,, A, C, F, I, L, N, O, P, R, RILUICCAPPINFO, RILUICCAPPINFO structure [Network Drivers Starting with Windows Vista], U, netvista.riluiccappinfo, ntddrilapitypes/RILUICCAPPINFO"
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
-	RILUICCAPPINFO
product: Windows
targetos: Windows
req.typenames: RILUICCAPPINFO, *LPRILUICCAPPINFO
---

# RILUICCAPPINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILUICCAPPINFO {
  DWORD           cbSize;
  DWORD           dwParams;
  HUICCAPP        hUiccApp;
  RILUICCAPPTYPE  dwUiccAppType;
  DWORD           dwAppIdLength;
  BYTE [32]       bAppId;
  DWORD           dwAppNameLength;
  char [256]      cszAppName;
  DWORD           dwNumPins;
  BYTE [8]        bPinRef;
} RILUICCAPPINFO, RILUICCAPPINFO;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field hUiccApp


### -field dwUiccAppType


### -field dwAppIdLength


### -field bAppId


### -field dwAppNameLength


### -field cszAppName


### -field dwNumPins


### -field bPinRef

