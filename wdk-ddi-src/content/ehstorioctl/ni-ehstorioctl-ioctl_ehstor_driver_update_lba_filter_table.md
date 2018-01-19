---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE
title: IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE
author: windows-driver-content
description: This IOCTL is used to inform the enhanced storage (EHSTOR) class driver of changes to the LBA filter table.
old-location: storage\ioctl_ehstor_driver_update_lba_filter_table.htm
old-project: storage
ms.assetid: 295EE3CC-4244-4411-9684-7C5D38B10EA9
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _PDO_TYPE, PDO_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE
req.alt-loc: EhStorIoctl.h
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
req.typenames: PDO_TYPE
---

# IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE IOCTL



## -description
This IOCTL is used to inform the enhanced storage (EHSTOR) class driver of changes to the LBA filter table. Bands managed by the silo  driver are composed of LBA ranges. The silo driver notifies the EHSTOR class driver of updates to the set of  bands it controls with this IOCTL.



## -ioctlparameters

### -input-buffer
The input buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> must contain a structure of type <a href="..\ehstorioctl\ns-ehstorioctl-_lba_filter_table.md">LBA_FILTER_TABLE</a>. This structure contains the filter table and the total entries it contains. An array <a href="..\ehstorioctl\ns-ehstorioctl-_lba_filter_table_entry.md">LBA_FILTER_TABLE_ENTRY</a> structure follows <b>LBA_FILTER_TABLE</b>.


### -input-buffer-length
The length of the buffer.


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
One of the following values can be returned in the <b>Status</b> field.

 


## -remarks
The LBA filters cannot overlap or be empty. The LBA filters do not have to be sorted in any way. 

If an LBA range is being unlocked, an <b>IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</b> request should be sent after the LBA range is unlocked on the storage device. Also,
 if an LBA range is currently being locked, <b>IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</b>  must be sent before the LBA range has been locked on the storage device.


## -see-also
<dl>
<dt>
<a href="..\ehstorioctl\ns-ehstorioctl-_lba_filter_table.md">LBA_FILTER_TABLE</a>
</dt>
<dt>
<a href="..\ehstorioctl\ns-ehstorioctl-_lba_filter_table_entry.md">LBA_FILTER_TABLE_ENTRY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

