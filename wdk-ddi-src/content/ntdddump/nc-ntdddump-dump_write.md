---
UID: NC:ntdddump.DUMP_WRITE
title: DUMP_WRITE (ntdddump.h)
description: The Dump_Write callback routine is called before the write to the dump port driver. The filter driver can access the dump data at this time.
old-location: storage\dump_write.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["DUMP_WRITE callback function"]
ms.keywords: Dump_Write, Dump_Write routine [Storage Devices], PDUMP_WRITE, filter_rtns_acfeabaa-fc01-494a-b344-c47d1fccd1ee.xml, ntdddump/Dump_Write, storage.dump_write
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
 - DUMP_WRITE
 - ntdddump/DUMP_WRITE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ntdddump.h
api_name:
 - Dump_Write
---

# DUMP_WRITE callback function


## -description

The <i>Dump_Write</i> callback routine is called before the write to the dump port driver. The filter driver can access the dump data at this time.

## -parameters

### -param FilterExtension 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/ntdddump/ns-ntdddump-_filter_extension">FILTER_EXTENSION</a> structure.

### -param DiskByteOffset 

[in, out]
The value, in bytes, relative to the destination partition for the crash dump or hibernation. Filter drivers should not modify this field.

### -param Mdl 

[in, out]
A pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a> structure that describes the data buffer. If the <b>MDL</b> is modified, the size of the write operation cannot change.

## -returns

If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values defined in <i>Ntstatus.h</i>.

## -remarks

Filter drivers can read the data that needs to be written. However, filter drivers cannot write to the buffer, as this could change the contents of the code or data that is being used by the crash dump process. Also, filter drivers are not allowed to change the size of the data.

To safely modify the data for the dump write, a filter driver should allocate a secondary buffer. The buffer's size will be the value of the <b>MaxPagesPerWrite</b> member of <a href="/windows-hardware/drivers/ddi/ntdddump/ns-ntdddump-_filter_initialization_data">FILTER_INITIALIZATION_DATA</a> multiplied by <b>PAGE_SIZE</b>. The data for the current buffer described by <i>Mdl</i> is copied into the secondary buffer and processed. After the filter is finished handling the dump data in the secondary buffer, the  <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a> pointed to by <i>Mdl</i> is updated with the address of the secondary buffer. The starting address of the secondary buffer set in the <b>MDL</b> must be page aligned.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdddump/nc-ntdddump-dump_read">Dump_Read</a>



<a href="/windows-hardware/drivers/ddi/ntdddump/ns-ntdddump-_filter_extension">FILTER_EXTENSION</a>



<a href="/windows-hardware/drivers/ddi/ntdddump/ns-ntdddump-_filter_initialization_data">FILTER_INITIALIZATION_DATA</a>
