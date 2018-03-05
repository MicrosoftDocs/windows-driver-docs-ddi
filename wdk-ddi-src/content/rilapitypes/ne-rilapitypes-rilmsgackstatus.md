---
UID: NE:rilapitypes.RILMSGACKSTATUS
title: RILMSGACKSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgackstatus_2.htm
old-project: netvista
ms.assetid: 412d9a0b-429b-4ce5-bf74-f602533174d7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILMSGACKSTATUS, RILMSGACKSTATUS enumeration [Network Drivers Starting with Windows Vista], RIL_MSGACKSTATUS_ERROR, RIL_MSGACKSTATUS_FAIL_MEM_FULL, RIL_MSGACKSTATUS_MAX, netvista.rilmsgackstatus_2, rilapitypes/RILMSGACKSTATUS, rilapitypes/RIL_MSGACKSTATUS_ERROR, rilapitypes/RIL_MSGACKSTATUS_FAIL_MEM_FULL, rilapitypes/RIL_MSGACKSTATUS_MAX
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILMSGACKSTATUS
product: Windows
targetos: Windows
req.typenames: RILMSGACKSTATUS
req.product: Windows 10 or later.
---

# RILMSGACKSTATUS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILMSGACKSTATUS { 
  RIL_MSGACKSTATUS_FAIL_MEM_FULL,
  RIL_MSGACKSTATUS_ERROR,
  RIL_MSGACKSTATUS_MAX
} RILMSGACKSTATUS;
````


## -enum-fields




### -field RIL_MSGACKSTATUS_STORED


### -field RIL_MSGACKSTATUS_FAIL_MEM_FULL


### -field RIL_MSGACKSTATUS_ERROR


### -field RIL_MSGACKSTATUS_MAX

