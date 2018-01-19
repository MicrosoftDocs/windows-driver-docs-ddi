---
UID: NS:bdatypes._BDA_CAS_CHECK_ENTITLEMENTTOKEN
title: _BDA_CAS_CHECK_ENTITLEMENTTOKEN
author: windows-driver-content
description: .
old-location: stream\bda_cas_check_entitlementtoken.htm
old-project: stream
ms.assetid: B6B645DF-AB4C-42FE-A664-AF9C9DD4F9E6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _BDA_CAS_CHECK_ENTITLEMENTTOKEN, *PBDA_CAS_CHECK_ENTITLEMENTTOKEN, BDA_CAS_CHECK_ENTITLEMENTTOKEN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BDA_CAS_CHECK_ENTITLEMENTTOKEN
req.alt-loc: Bdatypes.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PBDA_CAS_CHECK_ENTITLEMENTTOKEN, BDA_CAS_CHECK_ENTITLEMENTTOKEN
---

# _BDA_CAS_CHECK_ENTITLEMENTTOKEN structure



## -description




## -syntax

````
typedef struct _BDA_CAS_CHECK_ENTITLEMENTTOKEN {
  PBDARESULT lResult;
  ULONG      ulDescrambleStatus;
} BDA_CAS_CHECK_ENTITLEMENTTOKEN, *PBDA_CAS_CHECK_ENTITLEMENTTOKEN;
````


## -struct-fields

### -field lResult


### -field ulDescrambleStatus


## -remarks
