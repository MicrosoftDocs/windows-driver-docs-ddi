---
UID: NS:ntddrilapitypes.RILSMSMODIFICATIONINFO
title: RILSMSMODIFICATIONINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsmsmodificationinfo.htm
old-project: netvista
ms.assetid: 8fed32a2-f0a7-4462-b8bb-b01c9cccf6b7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILSMSMODIFICATIONINFO, RILSMSMODIFICATIONINFO, RILSMSMODIFICATIONINFO structure [Network Drivers Starting with Windows Vista], netvista.rilsmsmodificationinfo, ntddrilapitypes/RILSMSMODIFICATIONINFO"
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
-	RILSMSMODIFICATIONINFO
product: Windows
targetos: Windows
req.typenames: RILSMSMODIFICATIONINFO, *LPRILSMSMODIFICATIONINFO
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

