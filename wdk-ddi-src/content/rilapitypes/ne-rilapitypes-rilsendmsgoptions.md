---
UID: NE:rilapitypes.RILSENDMSGOPTIONS
title: RILSENDMSGOPTIONS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendmsgoptions_2.htm
old-project: netvista
ms.assetid: 84d13b43-06c4-4454-9853-80b1fe65d29d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilsendmsgoptions_2, RIL_SENDOPT_PERSISTLINK, RILSENDMSGOPTIONS enumeration [Network Drivers Starting with Windows Vista], RIL_SENDOPT_IMS, RILSENDMSGOPTIONS, rilapitypes/RIL_SENDOPT_IMS, rilapitypes/RILSENDMSGOPTIONS, rilapitypes/RIL_SENDOPT_PERSISTLINK
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
-	RILSENDMSGOPTIONS
product: Windows
targetos: Windows
req.typenames: RILSENDMSGOPTIONS
req.product: Windows 10 or later.
---

# RILSENDMSGOPTIONS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILSENDMSGOPTIONS { 
  RIL_SENDOPT_PERSISTLINK,
  RIL_SENDOPT_IMS
} RILSENDMSGOPTIONS;
````


## -enum-fields




### -field RIL_SENDOPT_NONE



### -field RIL_SENDOPT_PERSISTLINK



### -field RIL_SENDOPT_IMS


