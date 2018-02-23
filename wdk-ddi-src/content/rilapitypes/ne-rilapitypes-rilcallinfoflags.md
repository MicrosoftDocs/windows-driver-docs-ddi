---
UID: NE:rilapitypes.RILCALLINFOFLAGS
title: RILCALLINFOFLAGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfoflags_2.htm
old-project: netvista
ms.assetid: 7b701e86-ee0b-4a46-a6bf-4a4fe18c371f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILCALLINFO_FLAG_ALIENCALL, netvista.rilcallinfoflags_2, RILCALLINFO_FLAG_EMERGENCYCALL, RILCALLINFOFLAGS, rilapitypes/RILCALLINFO_FLAG_ALIENCALL, RILCALLINFOFLAGS enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RILCALLINFOFLAGS, rilapitypes/RILCALLINFO_FLAG_EMERGENCYCALL
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
-	RILCALLINFOFLAGS
product: Windows
targetos: Windows
req.typenames: RILCALLINFOFLAGS
req.product: Windows 10 or later.
---

# RILCALLINFOFLAGS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILCALLINFOFLAGS { 
  RILCALLINFO_FLAG_ALIENCALL,
  RILCALLINFO_FLAG_EMERGENCYCALL
} RILCALLINFOFLAGS;
````


## -enum-fields




### -field RILCALLINFO_FLAG_NONE


### -field RILCALLINFO_FLAG_ALIENCALL


### -field RILCALLINFO_FLAG_EMERGENCYCALL

