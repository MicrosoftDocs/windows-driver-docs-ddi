---
UID: NS:irb._IDE_REQUEST_BLOCK
title: "_IDE_REQUEST_BLOCK"
author: windows-driver-content
description: The IDE_REQUEST_BLOCK structure defines an IDE request block.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_request_block.htm
old-project: storage
ms.assetid: 9e112984-0a7e-4bb9-a10f-b50ab67ce4f3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PIDE_REQUEST_BLOCK, IDE_REQUEST_BLOCK, IDE_REQUEST_BLOCK structure [Storage Devices], PIDE_REQUEST_BLOCK, PIDE_REQUEST_BLOCK structure pointer [Storage Devices], _IDE_REQUEST_BLOCK, irb/IDE_REQUEST_BLOCK, irb/PIDE_REQUEST_BLOCK, storage.ide_request_block, structs-ATA_d1c6164f-8964-4e37-a9d4-9948215ed7cc.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: irb.h
req.include-header: Irb.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	irb.h
api_name:
-	IDE_REQUEST_BLOCK
product: Windows
targetos: Windows
req.typenames: IDE_REQUEST_BLOCK, *PIDE_REQUEST_BLOCK
---

# _IDE_REQUEST_BLOCK structure


## -description


The IDE_REQUEST_BLOCK structure defines an IDE request block.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field Function

Specifies the category that the request belongs to. The table below describes the classification of the I/O requests.

<table>
<tr>
<td>
<b>Function</b>

</td>
<td>
<b>Sub-commands</b>

</td>
<td>
<b>Description</b>

</td>
</tr>
<tr>
<td>
IRB_FUNCTION_ATA_COMMAND

</td>
<td>
IRB_FUNCTION_ATA_IDENTIFY

IRB_FUNCTION_ATA_READ

IRB_FUNCTION_ATA_WRITE

IRB_FUNCTION_ATA_FLUSH

IRB_FUNCTION_ATA_SMART

</td>
<td>
Indicates that the IRB contains an IdeTaskFile that describes the ATA command. The sub-commands indicate finer grouping of request for faster lookup.

</td>
</tr>
<tr>
<td>
IRB_FUNCTION_ATAPI_COMMAND

</td>
<td>
IRB_FUNCTION_REQUEST_SENSE

</td>
<td>
Indicates that the IRB contains a CDB that describes the ATAPI command.

</td>
</tr>
<tr>
<td>
IRB_FUNCTION_MINIPORT_COMMAND

</td>
<td>
IRB_FUNCTION_ADAPTER_FLUSH

IRB_FUNCTION_SHUTDOWN

IRB_FUNCTION_POWER_CHANGE

IRB_FUNCTION_POWER_REBOOT

IRB_FUNCTION_LUN_RESET

IRB_FUNCTION_MINIPORT_IOCTL

</td>
<td>
Indicates that the IRB is for the miniport. It is the responsibility of the miniport to interpret the command appropriately.

</td>
</tr>
</table>
 


### -field IrbStatus

The miniport must set this member to indicates the status of the specified operation. The table below describes the various <b>IrbStatus</b> values and their meaning.

<table>
<tr>
<td>
<b>Value</b>

</td>
<td>
<b>Meaning</b>

</td>
</tr>
<tr>
<td>
IRB_STATUS_PENDING

</td>
<td>
Indicates that the request is in progress. The port driver initializes <b>IrbStatus</b> to this value. A miniport driver should never set the <b>IrbStatus</b> member to this value.

</td>
</tr>
<tr>
<td>
IRB_STATUS_SUCCESS

</td>
<td>
Indicates that the request was completed successfully.

</td>
</tr>
<tr>
<td>
IRB_STATUS_DATALENGTH_MISMATCH

</td>
<td>
Indicates that a data underrun or overrun error occurred. The miniport must update the DataTransferLength field in the IRB to indicate the actual amount of data that was transferred in the case of an underrun.

</td>
</tr>
<tr>
<td>
IRB_STATUS_DEVICE_ERROR

</td>
<td>
Indicates that the device returned an error. The miniport driver must update the <i>AtaStatus</i> and <i>AtaError</i> fields in the Irb to the contents of the device ATA status and error register at the completion of the command.

</td>
</tr>
<tr>
<td>
IRB_STATUS_INVALID_REQUEST

</td>
<td>
Indicates that the miniport does not support the given request.

</td>
</tr>
<tr>
<td>
IRB_STATUS_BUS_RESET

</td>
<td>
Indicates that a bus reset occurred while processing the given request.

</td>
</tr>
<tr>
<td>
IRB_STATUS_SELECTION_TIMEOUT

</td>
<td>
Indicates that the destination device could not be selected.

</td>
</tr>
<tr>
<td>
IRB_STATUS_BUSY

</td>
<td>
Indicates that the device is busy. The port driver retries any request completed with this status. A request completed with busy status is retried only once. It is the responsibility of the miniport driver to pause the request queue using <b>AtaPortDeviceBusy</b> if the device cannot handle request for a certain period of time.

</td>
</tr>
<tr>
<td>
IRB_STATUS_AUTOSENSE_VALID

</td>
<td>
IRB_STATUS_AUTOSENSE_VALID is a bitmask that indicates valid sense data in the <i>SenseInfoBuffer</i> member of the IRB. 

</td>
</tr>
<tr>
<td>
IRB_STATUS_RETURN_TASKFILE_VALID

</td>
<td>
IRB_STATUS_RETURN_TASKFILE_VALID is a bitmask that indicates a valid return task file in the <i>SenseInfoBuffer</i> member of the IRB.

</td>
</tr>
</table>
 


### -field AtaStatus

Indicates the status returned by the device in its status register. The miniport driver should update this field when completing an IRB with <i>IRB_STATUS_DEVICE_ERROR</i>.


### -field AtaError

Indicates the error value returned by the device in its error register. The miniport driver should update this field when completing an IRB with <i>IRB_STATUS_DEVICE_ERROR</i>.


### -field Channel

Specifies the channel number.


### -field TargetId

Specifies the target ID of the device.


### -field Lun

Specifies the logical unit number of the device.


### -field CdbLength

Specifies the length in bytes of the buffer pointed to by <b>Cdb</b>.


### -field SenseInfoBufferLength

Specifies the length in bytes of the buffer pointed to by <b>SenseInfoBuffer</b>.


### -field SenseInfoBufferType

Specifies the type of data structure returned in <b>SenseInfoBuffer</b>. Because ATA commands don't have a need for the request sense command, ATA_PASS_THROUGH commands use <b>SenseInfoBuffer</b> to return task file information. For ATA_PASS_THROUGH commands, as identified in the <b>IrbFlags</b> member, the appropriate return <b>TaskFile</b> size should be reported as either SENSE_INFO_BUFFER_RETURN_TYPE_28BIT_TASKFILE or

SENSE_INFO_BUFFER_RETURN_TYPE_48BIT_TASKFILE.


### -field QueueTag

The queue tag for this IRB. The port driver sets this field to 0.


### -field ReservedAsUlong

Reserved for future use.


### -field IrbFlags

Qualifies the request with ceratin actions that need to be performed. The table below describes them in detail.

<table>
<tr>
<td>
<b>Flag</b>

</td>
<td>
<b>Description</b>

</td>
</tr>
<tr>
<td>
IRB_FLAGS_DRDY_REQUIRED

</td>
<td>
Indicates that the miniport driver must wait for the device to set the DRDY bit in the ATA status register before issuing this command.

</td>
</tr>
<tr>
<td>
IRB_FLAGS_USE_DMA

</td>
<td>
Indicates that the request has an associated scatter/gather list and the miniport driver could use DMA to transfer data for this request. 

</td>
</tr>
<tr>
<td>
IRB_FLAGS_MAP_BUFFERS

</td>
<td>
Indicates that the <b>DataBuffer</b> field in the IRB is mapped. The miniport can safely access <b>DataBuffer</b> when this flag is set. The miniport driver must not access <b>DataBuffer</b> if the flag is not set. The miniport driver could request the port driver to map the data buffer by setting this flag in the IRB in its <b>IdeHwBuildIo</b> routine.

</td>
</tr>
<tr>
<td>
IRB_FLAGS_48BIT

</td>
<td>
Indicates that the ATA command in the IRB belongs to the 48 bit LBA feature set. The <b>Previous</b> field in the <i>_IDE_TASK_FILE</i> structure is valid when this flag is set.

</td>
</tr>
<tr>
<td>
IRB_FLAGS_PIO_MULTIPLE

</td>
<td>
Indicates that the ATA command is to be transferred using the ATA PIO Multiple method.

</td>
</tr>
<tr>
<td>
IRB_FLAGS_RETURN_RESULTS

</td>
<td>
Indicates that the ATA return task file is to be copied to <b>SenseInfoBuffer</b>. 

</td>
</tr>
<tr>
<td>
IRB_FLAGS_DATA_IN

</td>
<td>
Indicates that the data is to be transferred from the device to the host system (a read operation).

</td>
</tr>
<tr>
<td>
IRB_FLAGS_DATA_OUT

</td>
<td>
Indicates that the data is to be transferred to the device from the host system ( a write operation).

</td>
</tr>
<tr>
<td>
IRB_FLAGS_DISCARDABLE  

</td>
<td>
Indicates that the command shall be done in a best effort manner. (note: this is not currently employed by ATAport).

</td>
</tr>
<tr>
<td>
IRB_FLAGS_HIGH_PRIORITY

</td>
<td>
Indicates that this IRB is to be processed as soon as possible, before non-high-priority IRBs currently in the ATA miniport.

</td>
</tr>
</table>
 


### -field TimeOutValue

Indicates the time in seconds after which the request will time out.


### -field DataTransferLength

Contains the length in bytes of the data buffer that contains data to be transferred.


### -field IrbExtension

Pointer to the per-request extension allocated by the port driver.


### -field DataBuffer

Pointer to the buffer where the data resides.


### -field SenseInfoBuffer

Pointer to the buffer which holds the sense data.


### -field NextIrb

Pointer to the next IRB to be processed. The port driver sets this to <b>NULL</b>. The miniport driver can use this field to link IRBs together.


### -field Reserved

Reserved for future use.


#### - IdeTaskFile

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff559144">IDE_TASK_FILE</a> that holds the IDE task file for the indicated controller. This member is defined whenever the result of a bitwise AND between the <b>Function</b> member and IRB_FUNCTION_ATA_COMMAND is nonzero.


#### - Cdb

Contains a command descriptor block (CDB). This member is defined whenever the result of a bitwise AND between the <b>Function</b> member and IRB_FUNCTION_ATAPI_COMMAND is nonzero.


#### - PowerChange

Indicates an enumeration value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff563909">POWER_CHANGE_INFO</a> that defines a power state transition. This member is defined whenever <b>Function</b> is equal to IRB_FUNCTION_POWER_CHANGE.


#### - AsUChar

Provides a means of accessing members <b>IdeTaskFile</b>, <b>PowerChange</b>, and <b>Cdb</b> as unsigned character data.


## -remarks



The IDE_REQUEST_BLOCK structure provides a functionality similar to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a> but with characteristics more suitable for managing devices on an IDE bus.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550155">AtaportDeviceBusy</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559144">IDE_TASK_FILE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563909">POWER_CHANGE_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IDE_REQUEST_BLOCK structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

