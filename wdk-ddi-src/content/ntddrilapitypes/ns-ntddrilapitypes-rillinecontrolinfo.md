---
UID: NS:ntddrilapitypes.RILLINECONTROLINFO
title: RILLINECONTROLINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rillinecontrolinfo.htm
old-project: netvista
ms.assetid: 4a3bcbda-58e8-4b40-bcc2-fe7b1e624973
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILLINECONTROLINFO, netvista.rillinecontrolinfo, RILLINECONTROLINFO, RILLINECONTROLINFO structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILLINECONTROLINFO"
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
-	RILLINECONTROLINFO
product: Windows
targetos: Windows
req.typenames: RILLINECONTROLINFO, *LPRILLINECONTROLINFO
---

# RILLINECONTROLINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILLINECONTROLINFO {
  DWORD  cbSize;
  DWORD  dwExecutor;
  BOOL   fPolarityIncluded;
  BOOL   fToggleMode;
  BOOL   fReversePolarity;
  DWORD  dwPowerDenialTime;
} RILLINECONTROLINFO, RILLINECONTROLINFO;
````


## -struct-fields




### -field cbSize


### -field dwExecutor


### -field fPolarityIncluded


### -field fToggleMode


### -field fReversePolarity


### -field dwPowerDenialTime

