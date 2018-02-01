---
UID: NS:ntddvdeo._ENG_EVENT
title: "_ENG_EVENT"
author: windows-driver-content
description: The ENG_EVENT structure is reserved for system use.
old-location: display\eng_event.htm
old-project: display
ms.assetid: 8c785e23-5b80-4518-8a90-3f46e8ad9b1d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: ntddvdeo/ENG_EVENT, ntddvdeo/PENG_EVENT, *PEVENT, PENG_EVENT, _ENG_EVENT, *PENG_EVENT, Video_Structs_a4ad3c78-3ef4-42b2-9640-ef253a74637b.xml, PENG_EVENT structure pointer [Display Devices], ENG_EVENT, display.eng_event, ENG_EVENT structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
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
-	ntddvdeo.h
apiname:
-	ENG_EVENT
product: Windows
targetos: Windows
req.typenames: "*PEVENT, *PENG_EVENT, ENG_EVENT"
---

# _ENG_EVENT structure


## -description


The ENG_EVENT structure is reserved for system use.


## -syntax


````
typedef struct _ENG_EVENT {
  PVOID pKEvent;
  ULONG fFlags;
} ENG_EVENT, *PENG_EVENT;
````


## -struct-fields




### -field pKEvent

Reserved for system use.


### -field fFlags

Reserved for system use.

