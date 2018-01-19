---
UID: NS:oemrilapitypes.RILDEVSPECIFICGETTOKEN
title: RILDEVSPECIFICGETTOKEN
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildevspecificgettoken.htm
old-project: netvista
ms.assetid: b0a534e0-1527-4ef3-a53f-c18cacbb5445
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILDEVSPECIFICGETTOKEN, *LPRILDEVSPECIFICGETTOKEN, RILDEVSPECIFICGETTOKEN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: oemrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILDEVSPECIFICGETTOKEN
req.alt-loc: oemrilapitypes.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *LPRILDEVSPECIFICGETTOKEN, RILDEVSPECIFICGETTOKEN
---

# RILDEVSPECIFICGETTOKEN structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILDEVSPECIFICGETTOKEN {
  DWORD                       cbSize;
  DWORD                       dwParams;
  DWORD                       dwTimeout;
  BYTE [GBA_PROTOCOL_ID_SIZE] bProtocolId;
  DWORD                       cbHeaderSize;
  BYTE []                     bHeader;
} RILDEVSPECIFICGETTOKEN, *LPRILDEVSPECIFICGETTOKEN;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwTimeout


### -field bProtocolId


### -field cbHeaderSize


### -field bHeader


## -remarks
