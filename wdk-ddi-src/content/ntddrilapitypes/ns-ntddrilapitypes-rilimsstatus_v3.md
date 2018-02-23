---
UID: NS:ntddrilapitypes.RILIMSSTATUS_V3
title: RILIMSSTATUS_V3
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsstatus_v3.htm
old-project: netvista
ms.assetid: 4c0ee205-2508-4414-afa5-cb6e7a358fc8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddrilapitypes/RILIMSSTATUS_V3, netvista.rilimsstatus_v3, *LPRILIMSSTATUS_V3, RILIMSSTATUS_V3, RILIMSSTATUS_V3 structure [Network Drivers Starting with Windows Vista], *LPRILIMSSTATUS, RILIMSSTATUS
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
-	RILIMSSTATUS_V3
product: Windows
targetos: Windows
req.typenames: RILIMSSTATUS_V3, *LPRILIMSSTATUS_V3, RILIMSSTATUS, *LPRILIMSSTATUS
---

# RILIMSSTATUS_V3 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILIMSSTATUS_V3 {
  DWORD             cbSize;
  DWORD             dwParams;
  DWORD             dwExecutor;
  HUICCAPP          hUiccApp;
  DWORD             dwAvailableServices;
  RILSMSFORMAT      dwSMSSupportedFormat;
  WCHAR [256]       wszServingDomain;
  RILIMSSYSTEMTYPE  dwIMSSystemType;
} RILIMSSTATUS_V3, RILIMSSTATUS_V3;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field hUiccApp


### -field dwAvailableServices


### -field dwSMSSupportedFormat


### -field wszServingDomain


### -field dwIMSSystemType

