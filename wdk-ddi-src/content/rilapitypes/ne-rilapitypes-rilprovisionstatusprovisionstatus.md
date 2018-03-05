---
UID: NE:rilapitypes.RILPROVISIONSTATUSPROVISIONSTATUS
title: RILPROVISIONSTATUSPROVISIONSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilprovisionstatusprovisionstatus_2.htm
old-project: netvista
ms.assetid: a0956046-766f-4cb0-9cf7-7cccdf929a2e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILPROVISIONSTATUSPROVISIONSTATUS, RILPROVISIONSTATUSPROVISIONSTATUS enumeration [Network Drivers Starting with Windows Vista], RIL_PROVISIONSTAT_BIP_STARTED, RIL_PROVISIONSTAT_BIP_SUCCESS, RIL_PROVISIONSTAT_FAILURE_END, RIL_PROVISIONSTAT_FAILURE_RETRY, RIL_PROVISIONSTAT_MAX, RIL_PROVISIONSTAT_NEEDED, RIL_PROVISIONSTAT_SUCCESS, netvista.rilprovisionstatusprovisionstatus_2, rilapitypes/RILPROVISIONSTATUSPROVISIONSTATUS, rilapitypes/RIL_PROVISIONSTAT_BIP_STARTED, rilapitypes/RIL_PROVISIONSTAT_BIP_SUCCESS, rilapitypes/RIL_PROVISIONSTAT_FAILURE_END, rilapitypes/RIL_PROVISIONSTAT_FAILURE_RETRY, rilapitypes/RIL_PROVISIONSTAT_MAX, rilapitypes/RIL_PROVISIONSTAT_NEEDED, rilapitypes/RIL_PROVISIONSTAT_SUCCESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILPROVISIONSTATUSPROVISIONSTATUS
product: Windows
targetos: Windows
req.typenames: RILPROVISIONSTATUSPROVISIONSTATUS
req.product: Windows 10 or later.
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

