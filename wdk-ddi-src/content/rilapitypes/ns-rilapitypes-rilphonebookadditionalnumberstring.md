---
UID: NS:rilapitypes.RILPHONEBOOKADDITIONALNUMBERSTRING
title: RILPHONEBOOKADDITIONALNUMBERSTRING
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookadditionalnumberstring_2.htm
old-project: netvista
ms.assetid: 06bd4e24-2859-4170-a02f-f97007b666e7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILPHONEBOOKADDITIONALNUMBERSTRING structure [Network Drivers Starting with Windows Vista], rilapitypes/RILPHONEBOOKADDITIONALNUMBERSTRING, RILPHONEBOOKADDITIONALNUMBERSTRING, netvista.rilphonebookadditionalnumberstring_2, *LPRILPHONEBOOKADDITIONALNUMBERSTRING
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
-	RILPHONEBOOKADDITIONALNUMBERSTRING
product: Windows
targetos: Windows
req.typenames: RILPHONEBOOKADDITIONALNUMBERSTRING, *LPRILPHONEBOOKADDITIONALNUMBERSTRING
req.product: Windows 10 or later.
---

# RILPHONEBOOKADDITIONALNUMBERSTRING structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILPHONEBOOKADDITIONALNUMBERSTRING {
  DWORD                           cbSize;
  DWORD                           dwNumId;
  WCHAR [MAXLENGTH_PHONEBOOKTEXT] wszText;
} RILPHONEBOOKADDITIONALNUMBERSTRING, RILPHONEBOOKADDITIONALNUMBERSTRING;
````


## -struct-fields




### -field cbSize


### -field dwNumId


### -field wszText

