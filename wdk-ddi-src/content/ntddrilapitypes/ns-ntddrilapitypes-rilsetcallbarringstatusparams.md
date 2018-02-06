---
UID: NS:ntddrilapitypes.RILSETCALLBARRINGSTATUSPARAMS
title: RILSETCALLBARRINGSTATUSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetcallbarringstatusparams.htm
old-project: netvista
ms.assetid: 1e524d3d-d9dc-4d95-ad13-258cd51bc532
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILSETCALLBARRINGSTATUSPARAMS, RILSETCALLBARRINGSTATUSPARAMS, RILSETCALLBARRINGSTATUSPARAMS structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILSETCALLBARRINGSTATUSPARAMS, netvista.rilsetcallbarringstatusparams"
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
-	RILSETCALLBARRINGSTATUSPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILSETCALLBARRINGSTATUSPARAMS, RILSETCALLBARRINGSTATUSPARAMS"
---

# RILSETCALLBARRINGSTATUSPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILSETCALLBARRINGSTATUSPARAMS {
  DWORD                             dwExecutor;
  RILCALLBARRINGSTATUSPARAMSTYPE    dwType;
  BOOL                              fAllClasses;
  DWORD                             dwInfoClasses;
  BOOL                              fPassword;
  char [256]                        szPassword;
  RILCALLBARRINGSTATUSPARAMSSTATUS  dwStatus;
} RILSETCALLBARRINGSTATUSPARAMS, RILSETCALLBARRINGSTATUSPARAMS;
````


## -struct-fields




### -field dwExecutor



### -field dwType



### -field fAllClasses



### -field dwInfoClasses



### -field fPassword



### -field szPassword



### -field dwStatus


