---
UID: NS:ehstorioctl._LBA_FILTER_TABLE
title: "_LBA_FILTER_TABLE"
author: windows-driver-content
description: The LBA_FILTER_TABLE structure contains the LBA ranges whose access is controlled by a silo driver.
old-location: storage\lba_filter_table.htm
tech.root: storage
ms.assetid: 656A413C-C0EF-4847-93F5-02DCCF40F348
ms.date: 3/29/2018
ms.keywords: "*PLBA_FILTER_TABLE, LBA_FILTER_TABLE, LBA_FILTER_TABLE structure [Storage Devices], PLBA_FILTER_TABLE, PLBA_FILTER_TABLE structure pointer [Storage Devices], _LBA_FILTER_TABLE, ehstorioctl/LBA_FILTER_TABLE, ehstorioctl/PLBA_FILTER_TABLE, storage.lba_filter_table"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	EhStorIoctl.h
api_name:
-	LBA_FILTER_TABLE
product:
- Windows
targetos: Windows
req.typenames: LBA_FILTER_TABLE, *PLBA_FILTER_TABLE
---

# _LBA_FILTER_TABLE structure


## -description


The <b>LBA_FILTER_TABLE</b> structure contains the LBA ranges whose access is controlled by a silo driver. The LBA filter entries in the table define bands on a storage device that are managed by a silo driver.  A silo drivers send the LBA filter table to the enhanced storage class driver in an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406723">IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</a> request.


## -struct-fields




### -field StructSize

The size of this structure. This is set to <b>sizeof</b>(LBA_FILTER_TABLE).


### -field GlobalReadLock

If TRUE, LBAs not included in the filter table are not readable. Otherwise unfiltered LBAs are readable if FALSE.


### -field Reserved1

Reserved.


### -field GlobalWriteLock

If TRUE, LBAs not included in the filter table are not writeable. Otherwise unfiltered LBAs are writeable if FALSE.


### -field Reserved2

Reserved.


### -field LbaFilterCount

The number of filter entries in the filter table.


### -field LbaFilterSize

The size in bytes of a filter table entry. This must be set to <b>sizeof</b>(LBA_FILTER_TABLE_ENTRY).


### -field LbaFiltersOffset

 




#### - LbaFilterOffset

The offset of the LBA filter table from the beginning of this structure. This will typically be <b>sizeof</b>(LBA_FILTER_TABLE).


## -remarks



LBA ranges not included in any filter table entries are considered part of the global band for the device. These ranges are managed independently by the Enhanced Storage Class driver. Access for these ranges is determined by the settings in <i>GlobalReadLock</i> and <i>GlobalWriteLock</i>.

Following the <b>LBA_FILTER_TABLE</b> structure is an array of 0 or more <a href="https://msdn.microsoft.com/library/windows/hardware/hh463962">LBA_FILTER_TABLE_ENTRY</a> structures. Each <b>LBA_FILTER_TABLE_ENTRY</b> defines an individual band whose access is controlled by the silo driver through the direction of band management requests forwarded by the Enhanced Storage Class driver. <b>LBA_FILTER_TABLE_ENTRY</b> structures can occur in any order, however, an LBA range in  a table entry must not overlap with an LBA range from another table entry. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406723">IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh463962">LBA_FILTER_TABLE_ENTRY</a>
 

 

