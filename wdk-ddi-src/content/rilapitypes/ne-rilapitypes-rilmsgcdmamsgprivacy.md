---
UID: NE:rilapitypes.RILMSGCDMAMSGPRIVACY
title: RILMSGCDMAMSGPRIVACY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmamsgprivacy_2.htm
old-project: netvista
ms.assetid: 1a143103-a952-410c-a143-153685f022dd
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_MSGPRIVACYCLASS_SECRET, netvista.rilmsgcdmamsgprivacy_2, rilapitypes/RILMSGCDMAMSGPRIVACY, RIL_MSGPRIVACYCLASS_RESTRICTED, rilapitypes/RIL_MSGPRIVACYCLASS_RESTRICTED, RIL_MSGPRIVACYCLASS_CONFIDENTIAL, rilapitypes/RIL_MSGPRIVACYCLASS_CONFIDENTIAL, RIL_MSGPRIVACYCLASS_SECRET, RIL_MSGPRIVACYCLASS_MAX, RILMSGCDMAMSGPRIVACY enumeration [Network Drivers Starting with Windows Vista], RILMSGCDMAMSGPRIVACY, rilapitypes/RIL_MSGPRIVACYCLASS_MAX
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
-	RILMSGCDMAMSGPRIVACY
product: Windows
targetos: Windows
req.typenames: RILMSGCDMAMSGPRIVACY
req.product: Windows 10 or later.
---

# RILMSGCDMAMSGPRIVACY enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILMSGCDMAMSGPRIVACY { 
  RIL_MSGPRIVACYCLASS_RESTRICTED,
  RIL_MSGPRIVACYCLASS_CONFIDENTIAL,
  RIL_MSGPRIVACYCLASS_SECRET,
  RIL_MSGPRIVACYCLASS_MAX
} RILMSGCDMAMSGPRIVACY;
````


## -enum-fields




### -field RIL_MSGPRIVACYCLASS_NOTRESTRICTED


### -field RIL_MSGPRIVACYCLASS_RESTRICTED


### -field RIL_MSGPRIVACYCLASS_CONFIDENTIAL


### -field RIL_MSGPRIVACYCLASS_SECRET


### -field RIL_MSGPRIVACYCLASS_MAX

