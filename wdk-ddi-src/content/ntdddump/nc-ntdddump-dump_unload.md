---
UID: NC:ntdddump.DUMP_UNLOAD
title: DUMP_UNLOAD (ntdddump.h)
description: The Dump_Unload callback routine is called when the dump stack is unloaded.
old-location: storage\dump_unload.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["DUMP_UNLOAD callback function"]
ms.keywords: Dump_Unload, Dump_Unload routine [Storage Devices], PDUMP_UNLOAD, filter_rtns_01414353-4ca7-409e-a360-a7ad69a57b40.xml, ntdddump/Dump_Unload, storage.dump_unload
req.header: ntdddump.h
req.include-header: Ntdddump.h
req.target-type: Desktop
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DUMP_UNLOAD
 - ntdddump/DUMP_UNLOAD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ntdddump.h
api_name:
 - DUMP_UNLOAD
---

# DUMP_UNLOAD callback function


## -description

The <i>Dump_Unload</i> callback routine is called when the dump stack is unloaded. For the dump stack, this routine is called when the crash dump functionality is disabled. For the hibernation stack, this routine is called after the system resumes from hibernation. This gives the filter driver an opportunity to free any resources that it may have allocated or do any clean-up required by the filter driver.

## -parameters

### -param FilterExtension [in]


A pointer to a <a href="/windows-hardware/drivers/ddi/ntdddump/ns-ntdddump-_filter_extension">FILTER_EXTENSION</a> structure.

## -returns

If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values defined in <i>Ntstatus.h</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdddump/ns-ntdddump-_filter_extension">FILTER_EXTENSION</a>

