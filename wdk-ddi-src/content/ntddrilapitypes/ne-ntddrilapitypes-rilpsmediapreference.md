---
UID: NE:ntddrilapitypes.RILPSMEDIAPREFERENCE
title: RILPSMEDIAPREFERENCE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpsmediapreference.htm
old-project: netvista
ms.assetid: a7fbef54-78c1-4696-8b0a-8c98d250f899
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILPSMEDIAPREFERENCE, RILPSMEDIAPREFERENCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILPSMEDIAPREFERENCE
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
req.typenames: RILPSMEDIAPREFERENCE
---

# RILPSMEDIAPREFERENCE enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILPSMEDIAPREFERENCE { 
  RIL_PSMPREF_WIFIONLY,
  RIL_PSMPREF_WIFIPREFERRED,
  RIL_PSMPREF_CELLONLY,
  RIL_PSMPREF_CELLPREFERRED,
  RIL_PSMPREF_NUMBER_OF_VALUES
} RILPSMEDIAPREFERENCE;
````


## -enum-fields

### -field RIL_PSMPREF_WIFIONLY


### -field RIL_PSMPREF_WIFIPREFERRED


### -field RIL_PSMPREF_CELLONLY


### -field RIL_PSMPREF_CELLPREFERRED


### -field RIL_PSMPREF_NUMBER_OF_VALUES


## -remarks
