---
UID: NE:rilapitypes.RILMSGDCSFLAGS
title: RILMSGDCSFLAGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgdcsflags_2.htm
old-project: netvista
ms.assetid: 1bb5a365-1f8f-41d4-a3f5-6a4a7238de03
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_DCSFLAG_DISCARD, RILMSGDCSFLAGS, rilapitypes/RIL_DCSFLAG_DISCARD, rilapitypes/RILMSGDCSFLAGS, RIL_DCSFLAG_INDICATIONACTIVE, RILMSGDCSFLAGS enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_DCSFLAG_INDICATIONACTIVE, rilapitypes/RIL_DCSFLAG_COMPRESSED, RIL_DCSFLAG_ALL, RIL_DCSFLAG_COMPRESSED, netvista.rilmsgdcsflags_2, rilapitypes/RIL_DCSFLAG_ALL
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
-	RILMSGDCSFLAGS
product: Windows
targetos: Windows
req.typenames: RILMSGDCSFLAGS
req.product: Windows 10 or later.
---

# RILMSGDCSFLAGS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILMSGDCSFLAGS { 
  RIL_DCSFLAG_COMPRESSED,
  RIL_DCSFLAG_INDICATIONACTIVE,
  RIL_DCSFLAG_DISCARD,
  RIL_DCSFLAG_ALL
} RILMSGDCSFLAGS;
````


## -enum-fields




### -field RIL_DCSFLAG_NONE



#### - RIL_DCSFLAG_COMPRESSED



#### - RIL_DCSFLAG_INDICATIONACTIVE



#### - RIL_DCSFLAG_DISCARD



#### - RIL_DCSFLAG_ALL


