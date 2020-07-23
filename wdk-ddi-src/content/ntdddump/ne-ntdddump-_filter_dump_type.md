---
UID: NE:ntdddump._FILTER_DUMP_TYPE
title: _FILTER_DUMP_TYPE (ntdddump.h)
description: The FILTER_DUMP_TYPE enumeration indicates the type of dump stack that this instance of the filter driver is loaded on.
old-location: storage\filter_dump_type.htm
tech.root: storage
ms.assetid: 396aec33-b4b4-4b4e-9890-b4aa829c3bbd
ms.date: 03/29/2018
keywords: ["_FILTER_DUMP_TYPE enumeration"]
ms.keywords: "*PFILTER_DUMP_TYPE, DumpTypeCrashdump, DumpTypeHibernation, DumpTypeUndefined, FILTER_DUMP_TYPE, FILTER_DUMP_TYPE enumeration [Storage Devices], PFILTER_DUMP_TYPE, PFILTER_DUMP_TYPE enumeration pointer [Storage Devices], _FILTER_DUMP_TYPE, ntdddump/DumpTypeCrashdump, ntdddump/DumpTypeHibernation, ntdddump/DumpTypeUndefined, ntdddump/FILTER_DUMP_TYPE, ntdddump/PFILTER_DUMP_TYPE, storage.filter_dump_type, structs-filter_b7846186-0937-4996-984e-398636fc7b2f.xml"
f1_keywords:
 - "ntdddump/FILTER_DUMP_TYPE"
 - "FILTER_DUMP_TYPE"
req.header: ntdddump.h
req.include-header: Ntdddump.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista and Windows Server 2008.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntdddump.h
api_name:
- FILTER_DUMP_TYPE
targetos: Windows
req.typenames: FILTER_DUMP_TYPE, *PFILTER_DUMP_TYPE
---

# _FILTER_DUMP_TYPE enumeration


## -description


The FILTER_DUMP_TYPE enumeration indicates the type of dump stack that this instance of the filter driver is loaded on.


## -enum-fields




### -field DumpTypeUndefined

This dump type is undefined.


### -field DumpTypeCrashdump

This dump type is for the crash dump stack.


### -field DumpTypeHibernation

This dump type is for hibernation.

