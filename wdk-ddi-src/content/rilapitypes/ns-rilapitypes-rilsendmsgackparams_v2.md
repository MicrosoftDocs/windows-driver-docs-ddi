---
UID: NS:rilapitypes.RILSENDMSGACKPARAMS_V2
title: RILSENDMSGACKPARAMS_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendmsgackparams_v2_2.htm
old-project: netvista
ms.assetid: 10bd2f88-ad1e-4d48-a338-e49c82a66d7a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSENDMSGACKPARAMS_V2, RILSENDMSGACKPARAMS, *LPRILSENDMSGACKPARAMS, RILSENDMSGACKPARAMS_V2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILSENDMSGACKPARAMS_V2
req.alt-loc: rilapitypes.h
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
req.typenames: RILSENDMSGACKPARAMS, *LPRILSENDMSGACKPARAMS, RILSENDMSGACKPARAMS_V2
req.product: Windows 10 or later.
---

# RILSENDMSGACKPARAMS_V2 structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILSENDMSGACKPARAMS_V2 {
  DWORD            cbSize;
  DWORD            dwExecutor;
  HUICCAPP         hUiccApp;
  DWORD            dwAckID;
  RILMSGACKSTATUS  dwMsgStatus;
  RILSMSFORMAT     dwSmsFormat;
  DWORD            dwOptions;
} RILSENDMSGACKPARAMS_V2, RILSENDMSGACKPARAMS_V2;
````


## -struct-fields

### -field cbSize


### -field dwExecutor


### -field hUiccApp


### -field dwAckID


### -field dwMsgStatus


### -field dwSmsFormat


### -field dwOptions


## -remarks
