---
UID: NS:rilapitypes.RILPHONEBOOKINFO
title: RILPHONEBOOKINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookinfo_2.htm
old-project: netvista
ms.assetid: bd302343-c9e3-4d1d-b991-ac19fbdb2da3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.rilphonebookinfo_2, RILPHONEBOOKINFO structure [Network Drivers Starting with Windows Vista], *LPRILPHONEBOOKINFO, RILPHONEBOOKINFO, rilapitypes/RILPHONEBOOKINFO
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
-	RILPHONEBOOKINFO
product: Windows
targetos: Windows
req.typenames: RILPHONEBOOKINFO, *LPRILPHONEBOOKINFO
req.product: Windows 10 or later.
---

# RILPHONEBOOKINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILPHONEBOOKINFO {
  DWORD  cbSize;
  DWORD  dwParams;
  DWORD  dwUsed;
  DWORD  dwTotal;
  DWORD  dwMaxAddressLength;
  DWORD  dwMaxTextLength;
  DWORD  dwMaxAdditionalNumbers;
  DWORD  dwMaxAdditionalNumberLength;
  DWORD  dwMaxAdditionalNumberTextLength;
  DWORD  dwUsedAdditionalNumberStrings;
  DWORD  dwTotalAdditionalNumberStrings;
  DWORD  dwMaxEmails;
  DWORD  dwMaxEmailAddressLength;
  DWORD  dwMaxGroups;
  DWORD  dwMaxGroupStringLength;
  DWORD  dwUsedGroupStrings;
  DWORD  dwTotalGroupStrings;
  DWORD  dwMaxSecondNameStringLength;
} RILPHONEBOOKINFO, RILPHONEBOOKINFO;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwUsed


### -field dwTotal


### -field dwMaxAddressLength


### -field dwMaxTextLength


### -field dwMaxAdditionalNumbers


### -field dwMaxAdditionalNumberLength


### -field dwMaxAdditionalNumberTextLength


### -field dwUsedAdditionalNumberStrings


### -field dwTotalAdditionalNumberStrings


### -field dwMaxEmails


### -field dwMaxEmailAddressLength


### -field dwMaxGroups


### -field dwMaxGroupStringLength


### -field dwUsedGroupStrings


### -field dwTotalGroupStrings


### -field dwMaxSecondNameStringLength

