---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE
title: IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE (ehstorioctl.h)
description: This IOCTL is used to inform the enhanced storage (EHSTOR) class driver of changes to the LBA filter table.
old-location: storage\ioctl_ehstor_driver_update_lba_filter_table.htm
tech.root: storage
ms.assetid: 295EE3CC-4244-4411-9684-7C5D38B10EA9
ms.date: 03/29/2018
ms.keywords: IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE, IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE control, IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE control code [Storage Devices], ehstorioctl/IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE, storage.ioctl_ehstor_driver_update_lba_filter_table
ms.topic: ioctl
f1_keywords:
 - "ehstorioctl/IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE"
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
- IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE IOCTL


## -description


This IOCTL is used to inform the enhanced storage (EHSTOR) class driver of changes to the LBA filter table. Bands managed by the silo  driver are composed of LBA ranges. The silo driver notifies the EHSTOR class driver of updates to the set of  bands it controls with this IOCTL.


## -ioctlparameters




### -input-buffer

The input buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> must contain a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ehstorioctl/ns-ehstorioctl-_lba_filter_table">LBA_FILTER_TABLE</a>. This structure contains the filter table and the total entries it contains. An array <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ehstorioctl/ns-ehstorioctl-_lba_filter_table_entry">LBA_FILTER_TABLE_ENTRY</a> structure follows <b>LBA_FILTER_TABLE</b>.


### -input-buffer-length

The length of the buffer.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

One of the following values can be returned in the <b>Status</b> field.

<table>
<tr>
<th>Status Value</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_SUCCESS</td>
<td>The LBA filter table was successfully updated.</td>
</tr>
<tr>
<td>STATUS_INVALID_BUFFER_SIZE</td>
<td>The input buffer length supplied is of incorrect size.</td>
</tr>
<tr>
<td>STATUS_INVALID_PARAMETER</td>
<td>The LBA filter count or an LBA range is specified incorrectly.</td>
</tr>
<tr>
<td>STATUS_INSUFFICIENT_RESOURCES</td>
<td>The IOCTL redirection list cannot be copied.</td>
</tr>
<tr>
<td>STATUS_NOT_SUPPORTED</td>
<td>The sending device is not a silo device or banding is not supported.</td>
</tr>
</table>
 


## -remarks



The LBA filters cannot overlap or be empty. The LBA filters do not have to be sorted in any way. 

If an LBA range is being unlocked, an <b>IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</b> request should be sent after the LBA range is unlocked on the storage device. Also,
 if an LBA range is currently being locked, <b>IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</b>  must be sent before the LBA range has been locked on the storage device.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ehstorioctl/ns-ehstorioctl-_lba_filter_table">LBA_FILTER_TABLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ehstorioctl/ns-ehstorioctl-_lba_filter_table_entry">LBA_FILTER_TABLE_ENTRY</a>
 

 

