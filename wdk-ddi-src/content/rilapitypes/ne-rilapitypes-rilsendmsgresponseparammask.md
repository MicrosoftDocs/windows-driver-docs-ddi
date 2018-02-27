---
UID: NE:rilapitypes.RILSENDMSGRESPONSEPARAMMASK
title: RILSENDMSGRESPONSEPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendmsgresponseparammask_2.htm
old-project: netvista
ms.assetid: 09711824-5a7a-4f24-bfe4-b7b146de7bee
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILSENDMSGRESPONSEPARAMMASK, RILSENDMSGRESPONSEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_MSGRES_ALL, RIL_PARAM_MSGRES_CDMACAUSECODE, RIL_PARAM_MSGRES_CDMAERRORCLASS, RIL_PARAM_MSGRES_GWLRELAYCODE, RIL_PARAM_MSGRES_GWLTRANSPORTCODE, RIL_PARAM_MSGRES_MSGID, netvista.rilsendmsgresponseparammask_2, rilapitypes/RILSENDMSGRESPONSEPARAMMASK, rilapitypes/RIL_PARAM_MSGRES_ALL, rilapitypes/RIL_PARAM_MSGRES_CDMACAUSECODE, rilapitypes/RIL_PARAM_MSGRES_CDMAERRORCLASS, rilapitypes/RIL_PARAM_MSGRES_GWLRELAYCODE, rilapitypes/RIL_PARAM_MSGRES_GWLTRANSPORTCODE, rilapitypes/RIL_PARAM_MSGRES_MSGID
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
-	RILSENDMSGRESPONSEPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILSENDMSGRESPONSEPARAMMASK
req.product: Windows 10 or later.
---

# RILSENDMSGRESPONSEPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILSENDMSGRESPONSEPARAMMASK { 
  RIL_PARAM_MSGRES_CDMACAUSECODE,
  RIL_PARAM_MSGRES_CDMAERRORCLASS,
  RIL_PARAM_MSGRES_GWLTRANSPORTCODE,
  RIL_PARAM_MSGRES_GWLRELAYCODE,
  RIL_PARAM_MSGRES_MSGID,
  RIL_PARAM_MSGRES_ALL
} RILSENDMSGRESPONSEPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_MSGRES_RETURN


### -field RIL_PARAM_MSGRES_CDMACAUSECODE


### -field RIL_PARAM_MSGRES_CDMAERRORCLASS


### -field RIL_PARAM_MSGRES_GWLTRANSPORTCODE


### -field RIL_PARAM_MSGRES_GWLRELAYCODE


### -field RIL_PARAM_MSGRES_MSGID


### -field RIL_PARAM_MSGRES_ALL

