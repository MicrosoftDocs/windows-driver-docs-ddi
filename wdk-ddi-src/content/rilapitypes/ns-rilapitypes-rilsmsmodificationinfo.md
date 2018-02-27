---
UID: NS:rilapitypes.RILSMSMODIFICATIONINFO
title: RILSMSMODIFICATIONINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsmsmodificationinfo_2.htm
old-project: netvista
ms.assetid: 64e5ea3d-a002-45df-b3ad-c8f723cbe54d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILSMSMODIFICATIONINFO, RILSMSMODIFICATIONINFO, RILSMSMODIFICATIONINFO structure [Network Drivers Starting with Windows Vista], netvista.rilsmsmodificationinfo_2, rilapitypes/RILSMSMODIFICATIONINFO"
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
-	RILSMSMODIFICATIONINFO
product: Windows
targetos: Windows
req.typenames: RILSMSMODIFICATIONINFO, *LPRILSMSMODIFICATIONINFO
req.product: Windows 10 or later.
---

# RILSMSMODIFICATIONINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILSMSMODIFICATIONINFO {
  DWORD               cbSize;
  DWORD               dwParams;
  DWORD               dwExecutor;
  DWORD               dwModificationType;
  RILADDRESS          raAddress;
  RILALPHAIDENTIFIER  aiIdentifier;
} RILSMSMODIFICATIONINFO, RILSMSMODIFICATIONINFO;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwModificationType


### -field raAddress


### -field aiIdentifier

