---
UID: NE:rilapitypes.RILINFOCLASS
title: RILINFOCLASS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilinfoclass_2.htm
old-project: netvista
ms.assetid: 19927cd1-8afa-4006-a882-d5222c690724
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_INFOCLASS_DATA, RIL_INFOCLASS_SMS, RIL_INFOCLASS_PACKETACCESS, rilapitypes/RIL_INFOCLASS_PADACCESS, rilapitypes/RIL_INFOCLASS_PACKETACCESS, rilapitypes/RIL_INFOCLASS_VOICE, RILINFOCLASS enumeration [Network Drivers Starting with Windows Vista], RILINFOCLASS, rilapitypes/RIL_INFOCLASS_DATACIRCUITASYNC, RIL_INFOCLASS_VOICE, rilapitypes/RILINFOCLASS, netvista.rilinfoclass_2, rilapitypes/RIL_INFOCLASS_DATACIRCUITSYNC, RIL_INFOCLASS_PADACCESS, RIL_INFOCLASS_DATACIRCUITSYNC, rilapitypes/RIL_INFOCLASS_ALL, rilapitypes/RIL_INFOCLASS_SMS, rilapitypes/RIL_INFOCLASS_FAX, rilapitypes/RIL_INFOCLASS_DATA, RIL_INFOCLASS_DATACIRCUITASYNC, RIL_INFOCLASS_FAX, RIL_INFOCLASS_ALL
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
-	RILINFOCLASS
product: Windows
targetos: Windows
req.typenames: RILINFOCLASS
req.product: Windows 10 or later.
---

# RILINFOCLASS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILINFOCLASS { 
  RIL_INFOCLASS_VOICE,
  RIL_INFOCLASS_DATA,
  RIL_INFOCLASS_FAX,
  RIL_INFOCLASS_SMS,
  RIL_INFOCLASS_DATACIRCUITSYNC,
  RIL_INFOCLASS_DATACIRCUITASYNC,
  RIL_INFOCLASS_PACKETACCESS,
  RIL_INFOCLASS_PADACCESS,
  RIL_INFOCLASS_ALL
} RILINFOCLASS;
````


## -enum-fields




### -field RIL_INFOCLASS_NONE



### -field RIL_INFOCLASS_VOICE



### -field RIL_INFOCLASS_DATA



### -field RIL_INFOCLASS_FAX



### -field RIL_INFOCLASS_SMS



### -field RIL_INFOCLASS_DATACIRCUITSYNC



### -field RIL_INFOCLASS_DATACIRCUITASYNC



### -field RIL_INFOCLASS_PACKETACCESS



### -field RIL_INFOCLASS_PADACCESS



### -field RIL_INFOCLASS_ALL


