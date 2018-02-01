---
UID: NS:ehstorioctl._LBA_FILTER_TABLE_ENTRY
title: "_LBA_FILTER_TABLE_ENTRY"
author: windows-driver-content
description: The LBA_FILTER_TABLE_ENTRY structure contains an individual LBA range for the LBA_FILTER_TABLE sent in an IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE request.
old-location: storage\lba_filter_table_entry.htm
old-project: storage
ms.assetid: 092B54D7-FFEA-48BB-993E-14443BD0C7AA
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PLBA_FILTER_TABLE_ENTRY structure pointer [Storage Devices], PLBA_FILTER_TABLE_ENTRY, LBA_FILTER_TABLE_ENTRY structure [Storage Devices], *PLBA_FILTER_TABLE_ENTRY, storage.lba_filter_table_entry, ehstorioctl/PLBA_FILTER_TABLE_ENTRY, LBA_FILTER_TABLE_ENTRY, _LBA_FILTER_TABLE_ENTRY, ehstorioctl/LBA_FILTER_TABLE_ENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	EhStorIoctl.h
apiname:
-	LBA_FILTER_TABLE_ENTRY
product: Windows
targetos: Windows
req.typenames: LBA_FILTER_TABLE_ENTRY, *PLBA_FILTER_TABLE_ENTRY
---

# _LBA_FILTER_TABLE_ENTRY structure


## -description


The <b>LBA_FILTER_TABLE_ENTRY</b> structure contains an individual LBA range for the <a href="..\ehstorioctl\ns-ehstorioctl-_lba_filter_table.md">LBA_FILTER_TABLE</a> sent in an <a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_driver_update_lba_filter_table.md">IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</a> request.


## -syntax


````
typedef struct _LBA_FILTER_TABLE_ENTRY {
  ULARGE_INTEGER StartLba;
  ULARGE_INTEGER LbaCount;
  BOOLEAN        ReadLock;
  BOOLEAN        WriteLock;
} LBA_FILTER_TABLE_ENTRY, *PLBA_FILTER_TABLE_ENTRY;
````


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


An LBA range is valid only if LbaCount is &gt; 0 and it is not overlapping with another entry in <a href="..\ehstorioctl\ns-ehstorioctl-_lba_filter_table.md">LBA_FILTER_TABLE</a>.



## -see-also

<a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_driver_update_lba_filter_table.md">IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</a>

<a href="..\ehstorioctl\ns-ehstorioctl-_lba_filter_table.md">LBA_FILTER_TABLE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20LBA_FILTER_TABLE_ENTRY structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

