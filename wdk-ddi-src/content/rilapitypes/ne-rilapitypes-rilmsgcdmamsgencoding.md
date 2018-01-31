---
UID: NE:rilapitypes.RILMSGCDMAMSGENCODING
title: RILMSGCDMAMSGENCODING
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmamsgencoding_2.htm
old-project: netvista
ms.assetid: 85586f69-09c3-4ebe-ad90-eb1b18e9d552
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_MSGCODING_OCTET, RIL_MSGCODING_JIS, rilapitypes/RILMSGCDMAMSGENCODING, rilapitypes/RIL_MSGCODING_8BITGSM, rilapitypes/RIL_MSGCODING_UNICODE, rilapitypes/RIL_MSGCODING_MAX, RILMSGCDMAMSGENCODING enumeration [Network Drivers Starting with Windows Vista], RIL_MSGCODING_7BITGSM, rilapitypes/RIL_MSGCODING_JIS, rilapitypes/RIL_MSGCODING_KOREAN, RIL_MSGCODING_LATIN, netvista.rilmsgcdmamsgencoding_2, rilapitypes/RIL_MSGCODING_7BITGSM, rilapitypes/RIL_MSGCODING_LATIN_HEBREW, rilapitypes/RIL_MSGCODING_LATIN, RILMSGCDMAMSGENCODING, rilapitypes/RIL_MSGCODING_IA5, RIL_MSGCODING_UNICODE, RIL_MSGCODING_7BITASCII, RIL_MSGCODING_LATIN_HEBREW, RIL_MSGCODING_KOREAN, RIL_MSGCODING_OCTET, rilapitypes/RIL_MSGCODING_7BITASCII, RIL_MSGCODING_IA5, RIL_MSGCODING_8BITGSM, RIL_MSGCODING_MAX
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
-	RILMSGCDMAMSGENCODING
product: Windows
targetos: Windows
req.typenames: RILMSGCDMAMSGENCODING
req.product: Windows 10 or later.
---

# RILMSGCDMAMSGENCODING enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILMSGCDMAMSGENCODING { 
  RIL_MSGCODING_7BITASCII,
  RIL_MSGCODING_UNICODE,
  RIL_MSGCODING_7BITGSM,
  RIL_MSGCODING_8BITGSM,
  RIL_MSGCODING_OCTET,
  RIL_MSGCODING_IA5,
  RIL_MSGCODING_JIS,
  RIL_MSGCODING_KOREAN,
  RIL_MSGCODING_LATIN_HEBREW,
  RIL_MSGCODING_LATIN,
  RIL_MSGCODING_MAX
} RILMSGCDMAMSGENCODING;
````


## -enum-fields




### -field RIL_MSGCODING_UNKNOWN



#### - RIL_MSGCODING_7BITASCII



#### - RIL_MSGCODING_UNICODE



#### - RIL_MSGCODING_7BITGSM



#### - RIL_MSGCODING_8BITGSM



#### - RIL_MSGCODING_OCTET



#### - RIL_MSGCODING_IA5



#### - RIL_MSGCODING_JIS



#### - RIL_MSGCODING_KOREAN



#### - RIL_MSGCODING_LATIN_HEBREW



#### - RIL_MSGCODING_LATIN



#### - RIL_MSGCODING_MAX


