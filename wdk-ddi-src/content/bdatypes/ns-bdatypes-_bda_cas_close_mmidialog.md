---
UID: NS:bdatypes._BDA_CAS_CLOSE_MMIDIALOG
title: _BDA_CAS_CLOSE_MMIDIALOG
author: windows-driver-content
description: .
old-location: stream\bda_cas_close_mmidialog.htm
old-project: stream
ms.assetid: 430580CF-F2FB-4684-B681-361E74D8EABD
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _BDA_CAS_CLOSE_MMIDIALOG, *PBDA_CAS_CLOSE_MMIDIALOG, BDA_CAS_CLOSE_MMIDIALOG
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
req.alt-api: BDA_CAS_CLOSE_MMIDIALOG
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
req.typenames: *PBDA_CAS_CLOSE_MMIDIALOG, BDA_CAS_CLOSE_MMIDIALOG
---

# _BDA_CAS_CLOSE_MMIDIALOG structure



## -description




## -syntax

````
typedef struct _BDA_CAS_CLOSE_MMIDIALOG {
  PBDARESULT lResult;
  ULONG      ulDescrambleStatus;
} BDA_CAS_CLOSE_MMIDIALOG, *PBDA_CAS_CLOSE_MMIDIALOG;
````


## -struct-fields

### -field lResult


### -field ulDescrambleStatus


## -remarks
