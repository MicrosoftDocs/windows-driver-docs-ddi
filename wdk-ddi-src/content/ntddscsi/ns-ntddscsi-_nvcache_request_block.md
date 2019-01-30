---
UID: NS:ntddscsi._NVCACHE_REQUEST_BLOCK
title: "_NVCACHE_REQUEST_BLOCK" (ntddscsi.h)
description: The NVCACHE_REQUEST_BLOCK structure is used in conjunction with the IOCTL_SCSI_MINIPORT request to manage hybrid-hard disk drive (H-HDD) devices (for example, Microsoft ReadyDrive technology).
old-location: storage\nvcache_request_block.htm
tech.root: storage
ms.assetid: 25ca2d81-72a5-47ae-bdfd-0ec63e1ca39a
ms.date: 03/29/2018
ms.keywords: "*PNVCACHE_REQUEST_BLOCK, NVCACHE_REQUEST_BLOCK, NVCACHE_REQUEST_BLOCK structure [Storage Devices], PNVCACHE_REQUEST_BLOCK, PNVCACHE_REQUEST_BLOCK structure pointer [Storage Devices], _NVCACHE_REQUEST_BLOCK, ntddscsi/NVCACHE_REQUEST_BLOCK, ntddscsi/PNVCACHE_REQUEST_BLOCK, storage.nvcache_request_block, structs-nvcache_1886905c-1d48-4cc9-b74c-3b52dc65b279.xml"
ms.topic: struct
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
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
-	ntddscsi.h
api_name:
-	NVCACHE_REQUEST_BLOCK
product:
- Windows
targetos: Windows
req.typenames: NVCACHE_REQUEST_BLOCK, *PNVCACHE_REQUEST_BLOCK
---

# _NVCACHE_REQUEST_BLOCK structure


## -description


The <b>NVCACHE_REQUEST_BLOCK</b> structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560512">IOCTL_SCSI_MINIPORT</a> request to manage hybrid-hard disk drive (H-HDD) devices (for example, Microsoft ReadyDrive technology). This topic defines the general structure for both input data and output data for a call made to the NV Cache Manager. A caller should fill all required fields before calling <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a>. The miniport driver must do the same after the requested function is completed, and before it returns.


## -struct-fields




### -field NRBSize

The <b>sizeof</b>(NVCACHE_REQUEST_BLOCK).


### -field Function

Specifies the operation to be performed, which can be one of the following values:





#### NRB_FUNCTION_NVCACHE_INFO

Get NV Cache Manager feature support information from the device. Upon the successful completion of this function, the required data fields are returned to the caller. The return data structure is <a href="https://msdn.microsoft.com/library/windows/hardware/ff563248">NV_FEATURE_PARAMETER</a>.



#### NRB_FUNCTION_SPINDLE_STATUS

Determine if the device is currently spinning up or spinning down. For an ATA device, a Check Power Mode command is required to obtain the device's spindle status. For a SCSI device, a Mode Sense command can be used to query the device's current power mode.



#### NRB_FUNCTION_NVCACHE_POWER_MODE_SET

Turn on the NV Cache Manager power mode.



#### NRB_FUNCTION_NVCACHE_POWER_MODE_RESET

Turn off the NV Cache Manager power mode.



#### NRB_FUNCTION_FLUSH_NVCACHE

Flush the data that is currently pinned in NV cache memory to make the required NV cache memory space available.



#### NRB_FUNCTION_QUERY_PINNED_SET

Get the Logical Block Address (LBA) ranges currently in the NV Cache Manager pinned set.



#### NRB_FUNCTION_QUERY_CACHE_MISS

Request that the device report NV Cache Misses in LBA ranges in a single 512-byte block.



#### NRB_FUNCTION_ADD_LBAS_PINNED_SET

Add the LBAs that are specified in the NV Cache Manager Set Data to the NV Cache Manager Pinned Set if they are not already.



#### NRB_FUNCTION_REMOVE_LBAS_PINNED_SET

Remove the LBAs that are specified in the NV Cache Set Data from the NV Cache pinned set.



#### NRB_FUNCTION_QUERY_HYBRID_DISK_STATUS

Reserved for future use.



#### NRB_FUNCTION_PASS_HINT_PAYLOAD

Pass IO hints to a SATA device.


### -field NRBFlags

Reserved for future use.


### -field NRBStatus

Indicates the NV Cache Manager function request status from the driver. There are seven possible values for this field:





#### NRB_SUCCESS

No error.



#### NRB_ILLEGAL_REQUEST

Illegal request detected by the port driver.



#### NRB_INVALID_PARAMETER

Invalid parameter passed to the port driver.



#### NRB_INPUT_DATA_OVERRUN

Too much data provided to the port driver.



#### NRB_INPUT_DATA_UNDERRUN

Not enough data provided to the port driver.



#### NRB_OUTPUT_DATA_OVERRUN

Too much data returned from the port driver.



#### NRB_OUTPUT_DATA_UNDERRUN

Not enough data returned from the port driver.


### -field Count

Number of 512-byte blocks to be transferred with the specified function.


### -field LBA

Starting LBA of the device for the specified function.


### -field DataBufSize

Size of the data buffer, in bytes.


### -field NVCacheStatus

Status returned from the device. For an ATA device, this value is the contents of the Status Register in its Task File. For a SCSI device, this value is the Sense Code returned from the device.


### -field NVCacheSubStatus

The error code returned from the device. For an ATA device, this value is the contents of the Error Register in its Task File. For a SCSI device, this value is the Sense key returned from the device.


## -remarks



For more information on function behavior, see section 7.20 of the <a href="https://go.microsoft.com/fwlink/p/?linkid=74996">ATA8-ACS specification</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560512">IOCTL_SCSI_MINIPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560517">IOCTL_SCSI_MINIPORT_NVCACHE</a>
 

 

