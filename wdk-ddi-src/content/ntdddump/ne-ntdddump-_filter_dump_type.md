---
UID: NE:ntdddump._FILTER_DUMP_TYPE
title: _FILTER_DUMP_TYPE
author: windows-driver-content
description: The FILTER_DUMP_TYPE enumeration indicates the type of dump stack that this instance of the filter driver is loaded on.
old-location: storage\filter_dump_type.htm
old-project: storage
ms.assetid: 396aec33-b4b4-4b4e-9890-b4aa829c3bbd
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _FILTER_DUMP_TYPE, FILTER_DUMP_TYPE, *PFILTER_DUMP_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntdddump.h
req.include-header: Ntdddump.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista and Windows Server 2008.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILTER_DUMP_TYPE
req.alt-loc: ntdddump.h
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
req.typenames: FILTER_DUMP_TYPE, *PFILTER_DUMP_TYPE
---

# _FILTER_DUMP_TYPE enumeration



## -description
The FILTER_DUMP_TYPE enumeration indicates the type of dump stack that this instance of the filter driver is loaded on.



## -syntax

````
typedef enum _FILTER_DUMP_TYPE { 
  DumpTypeUndefined    = 0,
  DumpTypeCrashdump    = 1,
  DumpTypeHibernation  = 2
} FILTER_DUMP_TYPE, *PFILTER_DUMP_TYPE;
````


## -enum-fields

### -field DumpTypeUndefined

This dump type is undefined.


### -field DumpTypeCrashdump

This dump type is for the crash dump stack.


### -field DumpTypeHibernation

This dump type is for hibernation.


## -remarks
