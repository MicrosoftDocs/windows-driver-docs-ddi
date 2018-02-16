---
UID: NE:rilapitypes.RILMSGOUTSUBMITVPFORMAT
title: RILMSGOUTSUBMITVPFORMAT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgoutsubmitvpformat_2.htm
old-project: netvista
ms.assetid: aa383bc9-935d-4883-929d-4ea58a1bf2c9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_MSGVP_ABSOLUTE, RILMSGOUTSUBMITVPFORMAT, rilapitypes/RILMSGOUTSUBMITVPFORMAT, rilapitypes/RIL_MSGVP_RELATIVE, RIL_MSGVP_RELATIVE, RIL_MSGVP_MAX, RILMSGOUTSUBMITVPFORMAT enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_MSGVP_MAX, netvista.rilmsgoutsubmitvpformat_2, rilapitypes/RIL_MSGVP_ENHANCED, rilapitypes/RIL_MSGVP_ABSOLUTE, RIL_MSGVP_ENHANCED
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
-	RILMSGOUTSUBMITVPFORMAT
product: Windows
targetos: Windows
req.typenames: RILMSGOUTSUBMITVPFORMAT
req.product: Windows 10 or later.
---

# RILMSGOUTSUBMITVPFORMAT enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILMSGOUTSUBMITVPFORMAT { 
  RIL_MSGVP_RELATIVE,
  RIL_MSGVP_ENHANCED,
  RIL_MSGVP_ABSOLUTE,
  RIL_MSGVP_MAX
} RILMSGOUTSUBMITVPFORMAT;
````


## -enum-fields




### -field RIL_MSGVP_NONE


### -field RIL_MSGVP_RELATIVE


### -field RIL_MSGVP_ENHANCED


### -field RIL_MSGVP_ABSOLUTE


### -field RIL_MSGVP_MAX

