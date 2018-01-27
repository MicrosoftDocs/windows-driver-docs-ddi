---
UID: NE:ntddrilapitypes.RILIMSFAILUREPARAMMASK
title: RILIMSFAILUREPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsfailureparammask.htm
old-project: netvista
ms.assetid: ba1542e9-da6f-4696-8f71-575000a7724e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_PARAM_IMSFAILURE_ALL, RIL_PARAM_IMSFAILURE_ERRORCODE, RILIMSFAILUREPARAMMASK, ntddrilapitypes/RIL_PARAM_IMSFAILURE_ERRORSTRING, RIL_PARAM_IMSFAILURE_ERRORSTRING, RILIMSFAILUREPARAMMASK enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILIMSFAILUREPARAMMASK, RIL_PARAM_IMSFAILURE_MESSAGESUBTYPE, ntddrilapitypes/RIL_PARAM_IMSFAILURE_MESSAGESUBTYPE, RIL_PARAM_IMSFAILURE_ALL, RIL_PARAM_IMSFAILURE_MESSAGETYPE, ntddrilapitypes/RIL_PARAM_IMSFAILURE_ERRORCODE, ntddrilapitypes/RIL_PARAM_IMSFAILURE_MESSAGETYPE, netvista.rilimsfailureparammask
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
-	RILIMSFAILUREPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILIMSFAILUREPARAMMASK
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


