---
UID: NE:rilapitypes.RILIMSFAILUREPARAMMASK
title: RILIMSFAILUREPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsfailureparammask_2.htm
old-project: netvista
ms.assetid: 07d651cd-b890-49cf-a543-2fc2fbf52412
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_PARAM_IMSFAILURE_MESSAGESUBTYPE, netvista.rilimsfailureparammask_2, rilapitypes/RIL_PARAM_IMSFAILURE_ALL, RIL_PARAM_IMSFAILURE_ALL, RIL_PARAM_IMSFAILURE_ERRORCODE, RILIMSFAILUREPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RILIMSFAILUREPARAMMASK, RIL_PARAM_IMSFAILURE_ERRORSTRING, RIL_PARAM_IMSFAILURE_MESSAGETYPE, RILIMSFAILUREPARAMMASK, rilapitypes/RIL_PARAM_IMSFAILURE_MESSAGESUBTYPE, rilapitypes/RIL_PARAM_IMSFAILURE_ERRORSTRING, rilapitypes/RIL_PARAM_IMSFAILURE_ERRORCODE, rilapitypes/RIL_PARAM_IMSFAILURE_MESSAGETYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.exe
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
-	RILIMSFAILUREPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILIMSFAILUREPARAMMASK
req.product: Windows 10 or later.
---

# RILIMSFAILUREPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILIMSFAILUREPARAMMASK { 
  RIL_PARAM_IMSFAILURE_MESSAGETYPE,
  RIL_PARAM_IMSFAILURE_MESSAGESUBTYPE,
  RIL_PARAM_IMSFAILURE_ERRORCODE,
  RIL_PARAM_IMSFAILURE_ERRORSTRING,
  RIL_PARAM_IMSFAILURE_ALL
} RILIMSFAILUREPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_IMSFAILURE_EXECUTOR



### -field RIL_PARAM_IMSFAILURE_MESSAGETYPE



### -field RIL_PARAM_IMSFAILURE_MESSAGESUBTYPE



### -field RIL_PARAM_IMSFAILURE_ERRORCODE



### -field RIL_PARAM_IMSFAILURE_ERRORSTRING



### -field RIL_PARAM_IMSFAILURE_ALL


