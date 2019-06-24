---
UID: NS:ehstorioctl._LBA_FILTER_TABLE_ENTRY
title: _LBA_FILTER_TABLE_ENTRY (ehstorioctl.h)
description: The LBA_FILTER_TABLE_ENTRY structure contains an individual LBA range for the LBA_FILTER_TABLE sent in an IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE request.
old-location: storage\lba_filter_table_entry.htm
tech.root: storage
ms.assetid: 092B54D7-FFEA-48BB-993E-14443BD0C7AA
ms.date: 03/29/2018
ms.keywords: "*PLBA_FILTER_TABLE_ENTRY, LBA_FILTER_TABLE_ENTRY, LBA_FILTER_TABLE_ENTRY structure [Storage Devices], PLBA_FILTER_TABLE_ENTRY, PLBA_FILTER_TABLE_ENTRY structure pointer [Storage Devices], _LBA_FILTER_TABLE_ENTRY, ehstorioctl/LBA_FILTER_TABLE_ENTRY, ehstorioctl/PLBA_FILTER_TABLE_ENTRY, storage.lba_filter_table_entry"
ms.topic: struct
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
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
- EhStorIoctl.h
api_name:
- LBA_FILTER_TABLE_ENTRY
product:
- Windows
targetos: Windows
req.typenames: LBA_FILTER_TABLE_ENTRY, *PLBA_FILTER_TABLE_ENTRY
---

# _LBA_FILTER_TABLE_ENTRY structure


## -description


The <b>LBA_FILTER_TABLE_ENTRY</b> structure contains an individual LBA range for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh463957">LBA_FILTER_TABLE</a> sent in an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406723">IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</a> request.


## -struct-fields




### -field StartLba

The starting LBA of the LBA range for this entry.


### -field LbaCount

The number of LBAs in the LBA range.


### -field ReadLock

Set to TRUE if the LBA range in this entry is  not readable. Otherwise, this member is FALSE and the LBA range is readable.


### -field WriteLock

Set to TRUE if the LBA range in this entry is  not writeable. Otherwise, this member is FALSE and the LBA range is writable


## -remarks



An LBA range is valid only if LbaCount is > 0 and it is not overlapping with another entry in <a href="https://msdn.microsoft.com/library/windows/hardware/hh463957">LBA_FILTER_TABLE</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406723">IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh463957">LBA_FILTER_TABLE</a>
 

 

