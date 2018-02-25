---
UID: NS:rilapitypes.RILIMSSTATUS_V2
title: RILIMSSTATUS_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsstatus_v2_2.htm
old-project: netvista
ms.assetid: 44aa62ac-510b-4f6d-9f17-f4abeadb06c1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILIMSSTATUS_V2, ,, 2, A, I, L, M, P, R, RILIMSSTATUS_V2, RILIMSSTATUS_V2 structure [Network Drivers Starting with Windows Vista], S, T, U, V, _, netvista.rilimsstatus_v2_2, rilapitypes/RILIMSSTATUS_V2"
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
-	RILIMSSTATUS_V2
product: Windows
targetos: Windows
req.typenames: RILIMSSTATUS_V2, *LPRILIMSSTATUS_V2
req.product: Windows 10 or later.
---

# RILIMSSTATUS_V2 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILIMSSTATUS_V2 {
  DWORD                     cbSize;
  DWORD                     dwParams;
  DWORD                     dwExecutor;
  HUICCAPP                  hUiccApp;
  DWORD                     dwAvailableServices;
  RILSMSFORMAT              dwSMSSupportedFormat;
  WCHAR [MAXLENGTH_ADDRESS] wszServingDomain;
} RILIMSSTATUS_V2, RILIMSSTATUS_V2;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field hUiccApp


### -field dwAvailableServices


### -field dwSMSSupportedFormat


### -field wszServingDomain

