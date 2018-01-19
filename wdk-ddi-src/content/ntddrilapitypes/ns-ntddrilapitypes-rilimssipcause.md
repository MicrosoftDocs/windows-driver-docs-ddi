---
UID: NS:ntddrilapitypes.RILIMSSIPCAUSE
title: RILIMSSIPCAUSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimssipcause.htm
old-project: netvista
ms.assetid: 79a57fc5-1526-4f18-b51c-7d045092fcb4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILIMSSIPCAUSE, *LPRILIMSSIPCAUSE, RILIMSSIPCAUSE
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
req.alt-api: RILIMSSIPCAUSE
req.alt-loc: ntddrilapitypes.h
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
req.typenames: *LPRILIMSSIPCAUSE, RILIMSSIPCAUSE
---

# RILIMSSIPCAUSE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILIMSSIPCAUSE {
  DWORD  dwCauseValue;
  DWORD  dwReasonValue;
} RILIMSSIPCAUSE, RILIMSSIPCAUSE;
````


## -struct-fields

### -field dwCauseValue


### -field dwReasonValue


## -remarks
