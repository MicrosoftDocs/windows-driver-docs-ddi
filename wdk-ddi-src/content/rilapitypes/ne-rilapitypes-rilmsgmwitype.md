---
UID: NE:rilapitypes.RILMSGMWITYPE
title: RILMSGMWITYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwitype_2.htm
old-project: netvista
ms.assetid: 55f06d11-60b7-4dc0-8f78-eb9901d49d1a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_MSGMWITYPE_VIDEOMAIL, RIL_MSGMWITYPE_PAGER, rilapitypes/RIL_MSGMWITYPE_FAX, netvista.rilmsgmwitype_2, rilapitypes/RIL_MSGMWITYPE_VOICEMAIL, RIL_MSGMWITYPE_VOICEMAIL, RIL_MSGMWITYPE_MULTIMEDIA, RIL_MSGMWITYPE_TEXT, rilapitypes/RIL_MSGMWITYPE_MAX, rilapitypes/RILMSGMWITYPE, RIL_MSGMWITYPE_MAX, rilapitypes/RIL_MSGMWITYPE_TEXT, RIL_MSGMWITYPE_FAX, RILMSGMWITYPE enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_MSGMWITYPE_VIDEOMAIL, rilapitypes/RIL_MSGMWITYPE_PAGER, RILMSGMWITYPE, rilapitypes/RIL_MSGMWITYPE_MULTIMEDIA
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
-	RILMSGMWITYPE
product: Windows
targetos: Windows
req.typenames: RILMSGMWITYPE
req.product: Windows 10 or later.
---

# RILMSGMWITYPE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILMSGMWITYPE { 
  RIL_MSGMWITYPE_VOICEMAIL,
  RIL_MSGMWITYPE_VIDEOMAIL,
  RIL_MSGMWITYPE_FAX,
  RIL_MSGMWITYPE_PAGER,
  RIL_MSGMWITYPE_MULTIMEDIA,
  RIL_MSGMWITYPE_TEXT,
  RIL_MSGMWITYPE_MAX
} RILMSGMWITYPE;
````


## -enum-fields




### -field RIL_MSGMWITYPE_NONE


### -field RIL_MSGMWITYPE_VOICEMAIL


### -field RIL_MSGMWITYPE_VIDEOMAIL


### -field RIL_MSGMWITYPE_FAX


### -field RIL_MSGMWITYPE_PAGER


### -field RIL_MSGMWITYPE_MULTIMEDIA


### -field RIL_MSGMWITYPE_TEXT


### -field RIL_MSGMWITYPE_MAX

