---
UID: NE:ntddrilapitypes.RILMESSAGEFLAGS
title: RILMESSAGEFLAGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessageflags.htm
old-project: netvista
ms.assetid: 82f36886-20bf-4981-b0f0-3871a87b6c4e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_MSGFLAG_STATUSREPORTRETURNED, ntddrilapitypes/RIL_MSGFLAG_CAUSEDBYCOMMAND, RILMESSAGEFLAGS enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_MSGFLAG_HEADER, RIL_MSGFLAG_CAUSEDBYCOMMAND, RIL_MSGFLAG_ALL, RIL_MSGFLAG_REPLYPATH, ntddrilapitypes/RIL_MSGFLAG_REJECTDUPS, RIL_MSGFLAG_HEADER, RIL_MSGFLAG_REJECTDUPS, netvista.rilmessageflags, ntddrilapitypes/RIL_MSGFLAG_STATUSREPORTRETURNED, RIL_MSGFLAG_MORETOSEND, RILMESSAGEFLAGS, ntddrilapitypes/RIL_MSGFLAG_MORETOSEND, ntddrilapitypes/RIL_MSGFLAG_ALL, ntddrilapitypes/RIL_MSGFLAG_STATUSREPORTREQUESTED, ntddrilapitypes/RIL_MSGFLAG_REPLYPATH, RIL_MSGFLAG_STATUSREPORTREQUESTED, ntddrilapitypes/RILMESSAGEFLAGS
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
-	RILMESSAGEFLAGS
product: Windows
targetos: Windows
req.typenames: RILMESSAGEFLAGS
---

# RILMESSAGEFLAGS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILMESSAGEFLAGS { 
  RIL_MSGFLAG_MORETOSEND,
  RIL_MSGFLAG_REPLYPATH,
  RIL_MSGFLAG_HEADER,
  RIL_MSGFLAG_REJECTDUPS,
  RIL_MSGFLAG_STATUSREPORTRETURNED,
  RIL_MSGFLAG_STATUSREPORTREQUESTED,
  RIL_MSGFLAG_CAUSEDBYCOMMAND,
  RIL_MSGFLAG_ALL
} RILMESSAGEFLAGS;
````


## -enum-fields




### -field RIL_MSGFLAG_NONE



### -field RIL_MSGFLAG_MORETOSEND



### -field RIL_MSGFLAG_REPLYPATH



### -field RIL_MSGFLAG_HEADER



### -field RIL_MSGFLAG_REJECTDUPS



### -field RIL_MSGFLAG_STATUSREPORTRETURNED



### -field RIL_MSGFLAG_STATUSREPORTREQUESTED



### -field RIL_MSGFLAG_CAUSEDBYCOMMAND



### -field RIL_MSGFLAG_ALL


