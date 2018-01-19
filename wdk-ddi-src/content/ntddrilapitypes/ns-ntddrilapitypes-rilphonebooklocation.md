---
UID: NS:ntddrilapitypes.RILPHONEBOOKLOCATION
title: RILPHONEBOOKLOCATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebooklocation.htm
old-project: netvista
ms.assetid: a4d47312-87e2-4147-94f6-ff9c9d452211
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILPHONEBOOKLOCATION, *LPRILPHONEBOOKLOCATION, RILPHONEBOOKLOCATION
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
req.alt-api: RILPHONEBOOKLOCATION
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
req.typenames: *LPRILPHONEBOOKLOCATION, RILPHONEBOOKLOCATION
---

# RILPHONEBOOKLOCATION structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILPHONEBOOKLOCATION {
  DWORD                       cbSize;
  HUICCAPP                    hUiccApp;
  RILPHONEENTRYSTORELOCATION  dwStoreLocation;
  DWORD                       dwIndex;
} RILPHONEBOOKLOCATION, RILPHONEBOOKLOCATION;
````


## -struct-fields

### -field cbSize


### -field hUiccApp


### -field dwStoreLocation


### -field dwIndex


## -remarks
