---
UID: NS:ntddrilapitypes.RILPHONEBOOKADDITIONALNUMBER
title: RILPHONEBOOKADDITIONALNUMBER
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookadditionalnumber.htm
old-project: netvista
ms.assetid: f90af220-6e48-49dd-b785-55da37894906
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddrilapitypes/RILPHONEBOOKADDITIONALNUMBER, *LPRILPHONEBOOKADDITIONALNUMBER, netvista.rilphonebookadditionalnumber, RILPHONEBOOKADDITIONALNUMBER, RILPHONEBOOKADDITIONALNUMBER structure [Network Drivers Starting with Windows Vista]
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
-	RILPHONEBOOKADDITIONALNUMBER
product: Windows
targetos: Windows
req.typenames: RILPHONEBOOKADDITIONALNUMBER, *LPRILPHONEBOOKADDITIONALNUMBER
---

# RILPHONEBOOKADDITIONALNUMBER structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILPHONEBOOKADDITIONALNUMBER {
  DWORD       cbSize;
  DWORD       dwParams;
  RILADDRESS  raAddress;
  DWORD       dwNumId;
} RILPHONEBOOKADDITIONALNUMBER, RILPHONEBOOKADDITIONALNUMBER;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field raAddress


### -field dwNumId

