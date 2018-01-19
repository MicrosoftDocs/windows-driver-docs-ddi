---
UID: NS:acpitabl._LPIT
title: _LPIT
author: windows-driver-content
description: Defines an LPI ACPI table.
old-location: acpi\lpit.htm
old-project: acpi
ms.assetid: 351BC859-E703-4F75-B691-A503C08560CF
ms.author: windowsdriverdev
ms.date: 12/31/2017
ms.keywords: _LPIT, LPIT, *PLPIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: acpitabl.h
req.include-header: Acpitabl.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: LPIT
req.alt-loc: acpitabl.h
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
req.typenames: LPIT, *PLPIT
---

# _LPIT structure



## -description
Defines an LPI ACPI table.



## -syntax

````
typedef struct _LPIT {
  DESCRIPTION_HEADER   Header;
  LPI_STATE_DESCRIPTOR LpiStates[ANYSIZE_ARRAY];
} LPIT, *PLPIT;
````


## -struct-fields

### -field Header

A header.


### -field LpiStates

An array of states.


## -remarks
