---
UID: NS:bdatypes._BDA_CAS_REQUESTTUNERDATA
title: _BDA_CAS_REQUESTTUNERDATA
author: windows-driver-content
description: .
old-location: stream\bda_cas_requesttunerdata.htm
old-project: stream
ms.assetid: 09347A56-C3F8-4E0D-A557-CECB7BBC7DB8
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _BDA_CAS_REQUESTTUNERDATA, *PBDA_CAS_REQUESTTUNERDATA, BDA_CAS_REQUESTTUNERDATA
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
req.alt-api: BDA_CAS_REQUESTTUNERDATA
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
req.typenames: *PBDA_CAS_REQUESTTUNERDATA, BDA_CAS_REQUESTTUNERDATA
---

# _BDA_CAS_REQUESTTUNERDATA structure



## -description




## -syntax

````
typedef struct _BDA_CAS_REQUESTTUNERDATA {
  UCHAR ucRequestPriority;
  UCHAR ucRequestReason;
  UCHAR ucRequestConsequences;
  ULONG ulEstimatedTime;
} BDA_CAS_REQUESTTUNERDATA, *PBDA_CAS_REQUESTTUNERDATA;
````


## -struct-fields

### -field ucRequestPriority


### -field ucRequestReason


### -field ucRequestConsequences


### -field ulEstimatedTime


## -remarks
