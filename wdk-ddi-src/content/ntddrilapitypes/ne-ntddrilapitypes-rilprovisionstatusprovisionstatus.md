---
UID: NE:ntddrilapitypes.RILPROVISIONSTATUSPROVISIONSTATUS
title: RILPROVISIONSTATUSPROVISIONSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilprovisionstatusprovisionstatus.htm
old-project: netvista
ms.assetid: ed7fc20a-b5d5-4dc6-ab95-5ee9258dbdae
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_PROVISIONSTAT_NEEDED, RIL_PROVISIONSTAT_BIP_STARTED, ntddrilapitypes/RIL_PROVISIONSTAT_FAILURE_RETRY, ntddrilapitypes/RIL_PROVISIONSTAT_FAILURE_END, ntddrilapitypes/RILPROVISIONSTATUSPROVISIONSTATUS, RIL_PROVISIONSTAT_BIP_SUCCESS, netvista.rilprovisionstatusprovisionstatus, RIL_PROVISIONSTAT_SUCCESS, ntddrilapitypes/RIL_PROVISIONSTAT_MAX, ntddrilapitypes/RIL_PROVISIONSTAT_BIP_STARTED, ntddrilapitypes/RIL_PROVISIONSTAT_BIP_SUCCESS, RILPROVISIONSTATUSPROVISIONSTATUS enumeration [Network Drivers Starting with Windows Vista], RIL_PROVISIONSTAT_FAILURE_END, RIL_PROVISIONSTAT_FAILURE_RETRY, ntddrilapitypes/RIL_PROVISIONSTAT_SUCCESS, ntddrilapitypes/RIL_PROVISIONSTAT_NEEDED, RIL_PROVISIONSTAT_MAX, RILPROVISIONSTATUSPROVISIONSTATUS
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
-	RILPROVISIONSTATUSPROVISIONSTATUS
product: Windows
targetos: Windows
req.typenames: RILPROVISIONSTATUSPROVISIONSTATUS
---

# RILPROVISIONSTATUSPROVISIONSTATUS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILPROVISIONSTATUSPROVISIONSTATUS { 
  RIL_PROVISIONSTAT_SUCCESS,
  RIL_PROVISIONSTAT_FAILURE_END,
  RIL_PROVISIONSTAT_FAILURE_RETRY,
  RIL_PROVISIONSTAT_NEEDED,
  RIL_PROVISIONSTAT_BIP_STARTED,
  RIL_PROVISIONSTAT_BIP_SUCCESS,
  RIL_PROVISIONSTAT_MAX
} RILPROVISIONSTATUSPROVISIONSTATUS;
````


## -enum-fields




### -field RIL_PROVISIONSTAT_STARTED



### -field RIL_PROVISIONSTAT_SUCCESS



### -field RIL_PROVISIONSTAT_FAILURE_END



### -field RIL_PROVISIONSTAT_FAILURE_RETRY



### -field RIL_PROVISIONSTAT_NEEDED



### -field RIL_PROVISIONSTAT_BIP_STARTED



### -field RIL_PROVISIONSTAT_BIP_SUCCESS



### -field RIL_PROVISIONSTAT_MAX


