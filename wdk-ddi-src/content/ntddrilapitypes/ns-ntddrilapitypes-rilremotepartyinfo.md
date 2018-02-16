---
UID: NS:ntddrilapitypes.RILREMOTEPARTYINFO
title: RILREMOTEPARTYINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilremotepartyinfo.htm
old-project: netvista
ms.assetid: 3bcaaf63-adff-4559-9e34-eae089dff6f8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILREMOTEPARTYINFO, *LPRILREMOTEPARTYINFO, ntddrilapitypes/RILREMOTEPARTYINFO, RILREMOTEPARTYINFO structure [Network Drivers Starting with Windows Vista], netvista.rilremotepartyinfo
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
-	RILREMOTEPARTYINFO
product: Windows
targetos: Windows
req.typenames: "*LPRILREMOTEPARTYINFO, RILREMOTEPARTYINFO"
---

# RILREMOTEPARTYINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILREMOTEPARTYINFO {
  DWORD                    cbSize;
  DWORD                    dwParams;
  DWORD                    dwExecutor;
  RILADDRESS               raAddress;
  RILSUBADDRESS            rsaSubAddress;
  WCHAR [256]              wszDescription;
  RILREMOTEPARTYINFOVALUE  dwNumberPresentationIndicator;
  RILREMOTEPARTYINFOVALUE  dwNamePresentationIndicator;
  DWORD                    dwID;
} RILREMOTEPARTYINFO, RILREMOTEPARTYINFO;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field raAddress


### -field rsaSubAddress


### -field wszDescription


### -field dwNumberPresentationIndicator


### -field dwNamePresentationIndicator


### -field dwID

