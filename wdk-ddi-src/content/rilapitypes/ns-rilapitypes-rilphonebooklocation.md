---
UID: NS:rilapitypes.RILPHONEBOOKLOCATION
title: RILPHONEBOOKLOCATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebooklocation_2.htm
old-project: netvista
ms.assetid: 1878109a-f70c-4e4b-8735-7fbb972f4416
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILPHONEBOOKLOCATION, RILPHONEBOOKLOCATION, RILPHONEBOOKLOCATION structure [Network Drivers Starting with Windows Vista], netvista.rilphonebooklocation_2, *LPRILPHONEBOOKLOCATION
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
-	rilapitypes.h
apiname:
-	RILPHONEBOOKLOCATION
product: Windows
targetos: Windows
req.typenames: "*LPRILPHONEBOOKLOCATION, RILPHONEBOOKLOCATION"
req.product: Windows 10 or later.
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


