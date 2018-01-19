---
UID: NS:bdatypes._BDA_CAS_OPENMMIDATA
title: _BDA_CAS_OPENMMIDATA
author: windows-driver-content
description: .
old-location: stream\bda_cas_openmmidata.htm
old-project: stream
ms.assetid: FAF30768-5DE4-4284-8CB5-2E518A2E37E7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _BDA_CAS_OPENMMIDATA, BDA_CAS_OPENMMIDATA, *PBDA_CAS_OPENMMIDATA
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
req.alt-api: BDA_CAS_OPENMMIDATA
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
req.typenames: BDA_CAS_OPENMMIDATA, *PBDA_CAS_OPENMMIDATA
---

# _BDA_CAS_OPENMMIDATA structure



## -description




## -syntax

````
typedef struct _BDA_CAS_OPENMMIDATA {
  ULONG  ulDialogNumber;
  ULONG  ulDialogRequest;
  GUID   uuidDialogType;
  USHORT usDialogDataLength;
  BYTE   argbDialogData[MIN_DIMENSION];
} BDA_CAS_OPENMMIDATA, *PBDA_CAS_OPENMMIDATA;
````


## -struct-fields

### -field ulDialogNumber


### -field ulDialogRequest


### -field uuidDialogType


### -field usDialogDataLength


### -field argbDialogData


## -remarks
