---
UID: NE:ntddrilapitypes.RILCALLWAITINGINFOPARAMMASK
title: RILCALLWAITINGINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallwaitinginfoparammask.htm
old-project: netvista
ms.assetid: 18fa3b00-8da7-4c83-a340-1515caffda01
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_PARAM_CWI_CALLERINFO, RILCALLWAITINGINFOPARAMMASK, RIL_PARAM_CWI_CALLERINFO, ntddrilapitypes/RIL_PARAM_CWI_ALL, RILCALLWAITINGINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_PARAM_CWI_CALLTYPE, netvista.rilcallwaitinginfoparammask, ntddrilapitypes/RILCALLWAITINGINFOPARAMMASK, RIL_PARAM_CWI_ALL, RIL_PARAM_CWI_CALLTYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	RILCALLWAITINGINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILCALLWAITINGINFOPARAMMASK
---

# RILCALLWAITINGINFOPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILCALLWAITINGINFOPARAMMASK { 
  RIL_PARAM_CWI_CALLTYPE,
  RIL_PARAM_CWI_CALLERINFO,
  RIL_PARAM_CWI_ALL
} RILCALLWAITINGINFOPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_CWI_EXECUTOR



### -field RIL_PARAM_CWI_CALLTYPE



### -field RIL_PARAM_CWI_CALLERINFO



### -field RIL_PARAM_CWI_ALL


