---
UID: NE:ntddrilapitypes.RILCALLMODIFICATIONINFOMODIFICATIONTYPE
title: RILCALLMODIFICATIONINFOMODIFICATIONTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmodificationinfomodificationtype.htm
old-project: netvista
ms.assetid: 37b18047-7818-4e57-b25a-3c958106e215
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_CALLMODIFICATIONTYPE_MAX, ntddrilapitypes/RIL_CALLMODIFICATIONTYPE_MODIFIED, RILCALLMODIFICATIONINFOMODIFICATIONTYPE enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_CALLMODIFICATIONTYPE_MAX, RIL_CALLMODIFICATIONTYPE_BLOCKED, ntddrilapitypes/RIL_CALLMODIFICATIONTYPE_BLOCKED, RILCALLMODIFICATIONINFOMODIFICATIONTYPE, netvista.rilcallmodificationinfomodificationtype, ntddrilapitypes/RILCALLMODIFICATIONINFOMODIFICATIONTYPE, RIL_CALLMODIFICATIONTYPE_MODIFIED
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
-	RILCALLMODIFICATIONINFOMODIFICATIONTYPE
product: Windows
targetos: Windows
req.typenames: RILCALLMODIFICATIONINFOMODIFICATIONTYPE
---

# RILCALLMODIFICATIONINFOMODIFICATIONTYPE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILCALLMODIFICATIONINFOMODIFICATIONTYPE { 
  RIL_CALLMODIFICATIONTYPE_BLOCKED,
  RIL_CALLMODIFICATIONTYPE_MODIFIED,
  RIL_CALLMODIFICATIONTYPE_MAX
} RILCALLMODIFICATIONINFOMODIFICATIONTYPE;
````


## -enum-fields




### -field RIL_CALLMODIFICATIONTYPE_UNKNOWN



### -field RIL_CALLMODIFICATIONTYPE_BLOCKED



### -field RIL_CALLMODIFICATIONTYPE_MODIFIED



### -field RIL_CALLMODIFICATIONTYPE_MAX


