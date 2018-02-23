---
UID: NE:ntddrilapitypes.RILCALLINFOFLAGS
title: RILCALLINFOFLAGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfoflags.htm
old-project: netvista
ms.assetid: c4edec8f-a001-491b-a3e6-03d19ac94f18
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILCALLINFOFLAGS, RILCALLINFO_FLAG_EMERGENCYCALL, netvista.rilcallinfoflags, ntddrilapitypes/RILCALLINFOFLAGS, ntddrilapitypes/RILCALLINFO_FLAG_EMERGENCYCALL, RILCALLINFO_FLAG_ALIENCALL, RILCALLINFOFLAGS enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILCALLINFO_FLAG_ALIENCALL
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
-	RILCALLINFOFLAGS
product: Windows
targetos: Windows
req.typenames: RILCALLINFOFLAGS
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

