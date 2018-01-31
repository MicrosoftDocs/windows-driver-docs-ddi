---
UID: NS:rilapitypes.RILRESETMODEMCONFIGITEM
title: RILRESETMODEMCONFIGITEM
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilresetmodemconfigitem_2.htm
old-project: netvista
ms.assetid: 9ac8f93e-4eac-47ec-bc1d-090abb339626
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILRESETMODEMCONFIGITEM structure [Network Drivers Starting with Windows Vista], *LPRILRESETMODEMCONFIGITEM, netvista.rilresetmodemconfigitem_2, RILRESETMODEMCONFIGITEM, rilapitypes/RILRESETMODEMCONFIGITEM
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
-	RILRESETMODEMCONFIGITEM
product: Windows
targetos: Windows
req.typenames: "*LPRILRESETMODEMCONFIGITEM, RILRESETMODEMCONFIGITEM"
req.product: Windows 10 or later.
---

# RILRESETMODEMCONFIGITEM structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILRESETMODEMCONFIGITEM {
  DWORD                     dwModemConfigItem;
  RILRESETMODEMCONFIGVALUE  rrmcValue;
} RILRESETMODEMCONFIGITEM, RILRESETMODEMCONFIGITEM;
````


## -struct-fields




#### - dwModemConfigItem



#### - rrmcValue


