---
UID: NS:rilapitypes.RILGETCALLBARRINGSTATUSPARAMS
title: RILGETCALLBARRINGSTATUSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetcallbarringstatusparams_2.htm
old-project: netvista
ms.assetid: 1a33d682-5413-4026-8e43-e83548f688c5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilgetcallbarringstatusparams_2, RILGETCALLBARRINGSTATUSPARAMS structure [Network Drivers Starting with Windows Vista], RILGETCALLBARRINGSTATUSPARAMS, rilapitypes/RILGETCALLBARRINGSTATUSPARAMS, *LPRILGETCALLBARRINGSTATUSPARAMS
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
-	RILGETCALLBARRINGSTATUSPARAMS
product: Windows
targetos: Windows
req.typenames: *LPRILGETCALLBARRINGSTATUSPARAMS, RILGETCALLBARRINGSTATUSPARAMS
req.product: Windows 10 or later.
---

# RILGETCALLBARRINGSTATUSPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILGETCALLBARRINGSTATUSPARAMS {
  DWORD                           dwExecutor;
  RILCALLBARRINGSTATUSPARAMSTYPE  dwType;
  BOOL                            fAllClasses;
  DWORD                           dwInfoClasses;
} RILGETCALLBARRINGSTATUSPARAMS, RILGETCALLBARRINGSTATUSPARAMS;
````


## -struct-fields




### -field dwExecutor



### -field dwType



### -field fAllClasses



### -field dwInfoClasses


