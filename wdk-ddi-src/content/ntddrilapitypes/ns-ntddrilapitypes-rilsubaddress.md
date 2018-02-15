---
UID: NS:ntddrilapitypes.RILSUBADDRESS
title: RILSUBADDRESS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsubaddress.htm
old-project: netvista
ms.assetid: 0a1f9e89-df17-4802-9685-06a2eedbc0e5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSUBADDRESS structure [Network Drivers Starting with Windows Vista], *LPRILSUBADDRESS, netvista.rilsubaddress, RILSUBADDRESS, ntddrilapitypes/RILSUBADDRESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	RILSUBADDRESS
product: Windows
targetos: Windows
req.typenames: "*LPRILSUBADDRESS, RILSUBADDRESS"
---

# RILSUBADDRESS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILSUBADDRESS {
  DWORD              cbSize;
  DWORD              dwParams;
  RILSUBADDRESSTYPE  dwType;
  WCHAR [256]        wszSubAddress;
} RILSUBADDRESS, RILSUBADDRESS;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwType


### -field wszSubAddress

