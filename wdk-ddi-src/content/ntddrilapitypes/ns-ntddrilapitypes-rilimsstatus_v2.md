---
UID: NS:ntddrilapitypes.RILIMSSTATUS_V2
title: RILIMSSTATUS_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsstatus_v2.htm
old-project: netvista
ms.assetid: afc17375-a65d-495d-b68a-b74146cb8f69
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILIMSSTATUS_V2, netvista.rilimsstatus_v2, RILIMSSTATUS_V2 structure [Network Drivers Starting with Windows Vista], *LPRILIMSSTATUS_V2, RILIMSSTATUS_V2
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
-	RILIMSSTATUS_V2
product: Windows
targetos: Windows
req.typenames: "*LPRILIMSSTATUS_V2, RILIMSSTATUS_V2"
---

# RILIMSSTATUS_V2 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILIMSSTATUS_V2 {
  DWORD         cbSize;
  DWORD         dwParams;
  DWORD         dwExecutor;
  HUICCAPP      hUiccApp;
  DWORD         dwAvailableServices;
  RILSMSFORMAT  dwSMSSupportedFormat;
  WCHAR [256]   wszServingDomain;
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


