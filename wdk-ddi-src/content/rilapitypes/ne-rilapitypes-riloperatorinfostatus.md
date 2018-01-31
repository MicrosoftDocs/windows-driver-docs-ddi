---
UID: NE:rilapitypes.RILOPERATORINFOSTATUS
title: RILOPERATORINFOSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riloperatorinfostatus_2.htm
old-project: netvista
ms.assetid: 8b17ae4a-b3ea-48b6-8269-f947e1d74b86
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILOPERATORINFOSTATUS, RILOPERATORINFOSTATUS enumeration [Network Drivers Starting with Windows Vista], RIL_OPSTATUS_AVAILABLE, RIL_OPSTATUS_CURRENT, rilapitypes/RIL_OPSTATUS_CURRENT, RILOPERATORINFOSTATUS, RIL_OPSTATUS_MAX, rilapitypes/RIL_OPSTATUS_MAX, rilapitypes/RIL_OPSTATUS_AVAILABLE, RIL_OPSTATUS_FORBIDDEN, rilapitypes/RIL_OPSTATUS_FORBIDDEN, netvista.riloperatorinfostatus_2
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
-	RILOPERATORINFOSTATUS
product: Windows
targetos: Windows
req.typenames: RILOPERATORINFOSTATUS
req.product: Windows 10 or later.
---

# RILOPERATORINFOSTATUS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILOPERATORINFOSTATUS { 
  RIL_OPSTATUS_AVAILABLE,
  RIL_OPSTATUS_CURRENT,
  RIL_OPSTATUS_FORBIDDEN,
  RIL_OPSTATUS_MAX
} RILOPERATORINFOSTATUS;
````


## -enum-fields




### -field RIL_OPSTATUS_UNKNOWN



#### - RIL_OPSTATUS_AVAILABLE



#### - RIL_OPSTATUS_CURRENT



#### - RIL_OPSTATUS_FORBIDDEN



#### - RIL_OPSTATUS_MAX


