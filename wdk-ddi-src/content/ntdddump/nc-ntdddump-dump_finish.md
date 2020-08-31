---
UID: NC:ntdddump.DUMP_FINISH
title: DUMP_FINISH (ntdddump.h)
description: The Dump_Finish callback routine is called after writing all the dump data. The dump port driver generally flushes the cache to ensure the data is stored on the storage media before the system powers down.
old-location: storage\dump_finish.htm
tech.root: storage
ms.assetid: 6e267810-a7ad-4407-8d01-4a2cad7a37bc
ms.date: 03/29/2018
keywords: ["DUMP_FINISH callback function"]
ms.keywords: Dump_Finish, Dump_Finish routine [Storage Devices], PDUMP_FINISH, filter_rtns_7d5c92a4-19b6-4ef1-9b86-a9ec250106ef.xml, ntdddump/Dump_Finish, storage.dump_finish
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
 - DUMP_FINISH
 - ntdddump/DUMP_FINISH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ntdddump.h
api_name:
 - Dump_Finish
---

# DUMP_FINISH callback function


## -description

The <i>Dump_Finish</i> callback routine is called after writing all the dump data. The dump port driver generally flushes the cache to ensure the data is stored on the storage media before the system powers down.

## -parameters

### -param FilterExtension 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddump/ns-ntdddump-_filter_extension">FILTER_EXTENSION</a> structure.

## -returns

If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values defined in <i>Ntstatus.h</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddump/ns-ntdddump-_filter_extension">FILTER_EXTENSION</a>

