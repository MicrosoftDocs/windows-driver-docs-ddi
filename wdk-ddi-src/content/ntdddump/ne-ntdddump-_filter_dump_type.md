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
ms.keywords: ntdddump/DumpTypeCrashdump, FILTER_DUMP_TYPE, PFILTER_DUMP_TYPE enumeration pointer [Storage Devices], structs-filter_b7846186-0937-4996-984e-398636fc7b2f.xml, ntdddump/DumpTypeHibernation, _FILTER_DUMP_TYPE, *PFILTER_DUMP_TYPE, ntdddump/FILTER_DUMP_TYPE, DumpTypeHibernation, ntdddump/DumpTypeUndefined, DumpTypeUndefined, DumpTypeCrashdump, PFILTER_DUMP_TYPE, storage.filter_dump_type, FILTER_DUMP_TYPE enumeration [Storage Devices], ntdddump/PFILTER_DUMP_TYPE
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
-	ntdddump.h
apiname: 
-	FILTER_DUMP_TYPE
product: Windows
targetos: Windows
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

