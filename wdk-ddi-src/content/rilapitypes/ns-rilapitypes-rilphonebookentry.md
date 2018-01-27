---
UID: NS:rilapitypes.RILPHONEBOOKENTRY
title: RILPHONEBOOKENTRY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookentry_2.htm
old-project: netvista
ms.assetid: 848afbe3-be29-4c20-b9d0-33db98dab7bb
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILPHONEBOOKENTRY, netvista.rilphonebookentry_2, RILPHONEBOOKENTRY structure [Network Drivers Starting with Windows Vista], rilapitypes/RILPHONEBOOKENTRY, *LPRILPHONEBOOKENTRY
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
-	RILPHONEBOOKENTRY
product: Windows
targetos: Windows
req.typenames: *LPRILPHONEBOOKENTRY, RILPHONEBOOKENTRY
req.product: Windows 10 or later.
---

# RILPHONEBOOKENTRY structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILPHONEBOOKENTRY {
  DWORD                           cbSize;
  DWORD                           dwParams;
  DWORD                           dwIndex;
  RILADDRESS                      raAddress;
  WCHAR [MAXLENGTH_PHONEBOOKTEXT] wszText;
  WCHAR [MAXLENGTH_PHONEBOOKTEXT] wszSecondName;
  DWORD                           dwGroupIdCount;
  DWORD [MAXNUM_GROUPS]           rgdwGroupId;
  DWORD                           dwAdditionalNumCount;
  DWORD                           dwAdditionalNumSize;
  DWORD                           dwAdditionalNumOffset;
  DWORD                           dwEmailCount;
  DWORD                           dwEmailSize;
  DWORD                           dwEmailOffset;
} RILPHONEBOOKENTRY, RILPHONEBOOKENTRY;
````


## -struct-fields




### -field cbSize



### -field dwParams



### -field dwIndex



### -field raAddress



### -field wszText



### -field wszSecondName



### -field dwGroupIdCount



### -field rgdwGroupId



### -field dwAdditionalNumCount



### -field dwAdditionalNumSize



### -field dwAdditionalNumOffset



### -field dwEmailCount



### -field dwEmailSize



### -field dwEmailOffset


