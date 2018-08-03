---
UID: NS:ntddstor._DEVICE_DATA_SET_LB_PROVISIONING_STATE
title: "_DEVICE_DATA_SET_LB_PROVISIONING_STATE"
author: windows-driver-content
description: The DEVICE_DATA_SET_LB_PROVISIONING_STATE structure is returned by an IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request when requesting logical block provisioning information for a data set range.
old-location: storage\device_data_set_lb_provisioning_state.htm
tech.root: storage
ms.assetid: 99FBD363-0999-4AEE-A222-69C0FB71D248
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDEVICE_DATA_SET_LB_PROVISIONING_STATE, DEVICE_DATA_SET_LB_PROVISIONING_STATE, DEVICE_DATA_SET_LB_PROVISIONING_STATE structure [Storage Devices], PDEVICE_DATA_SET_LB_PROVISIONING_STATE, PDEVICE_DATA_SET_LB_PROVISIONING_STATE structure pointer [Storage Devices], _DEVICE_DATA_SET_LB_PROVISIONING_STATE, ntddstor/DEVICE_DATA_SET_LB_PROVISIONING_STATE, ntddstor/PDEVICE_DATA_SET_LB_PROVISIONING_STATE, storage.device_data_set_lb_provisioning_state"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	ntddstor.h
api_name:
-	DEVICE_DATA_SET_LB_PROVISIONING_STATE
product:
- Windows
targetos: Windows
req.typenames: DEVICE_DATA_SET_LB_PROVISIONING_STATE, *PDEVICE_DATA_SET_LB_PROVISIONING_STATE
---

# _DEVICE_DATA_SET_LB_PROVISIONING_STATE structure


## -description


The <b>DEVICE_DATA_SET_LB_PROVISIONING_STATE</b> structure is returned by an  <a href="https://msdn.microsoft.com/library/windows/hardware/ff560573">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> request when requesting logical block  provisioning information for a data set range.


## -struct-fields




### -field Size

The size of this structure, including the slab allocation bitmap, in bytes.


### -field Version

The version of this structure.


### -field SlabSizeInBytes

The size, in bytes, of a slab.


### -field SlabOffsetDeltaInBytes

The difference, in bytes, from the offset specified in the data set range to the starting slab position.


### -field SlabAllocationBitMapBitCount

The number of bits  in the allocation bitmap mapping  slabs for the data set range.


### -field SlabAllocationBitMapLength

The number of <b>ULONG</b> array values containing the slab allocation bitmap.


### -field SlabAllocationBitMap

A bitmap of slab allocations.


## -remarks



Provisioning state information is returned when the <b>Action</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff552527">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> is set to <b>DeviceDsmAction_Allocation</b>. The caller should include only one data set range in the system buffer at <b>DataSetRangesOffset</b>.

On return, the system buffer contains a <a href="https://msdn.microsoft.com/FFC52136-8A1C-48F6-A846-C1C5BFB4570C">DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUPUT</a> structure followed by the <b>DEVICE_DATA_SET_LB_PROVISIONING_STATE</b> structure. The <b>DEVICE_DATA_SET_LB_PROVISIONING_STATE</b> structure begins at an offset from the beginning of the system buffer specified by <b>OutputBlockOffset</b> in <b>DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUPUT</b>.

Each bit in the allocation bitmap represents a slab mapping within the data set range requested. The bits correspond directly to the slabs in the data set range. This means that bit 0 in the bitmap marks the first slab in the range. A slab is mapped if the bit value = 1 and unmapped if the bit value = 0.

Space for <b>SlabAllocationBitMap</b> should be allocated based on the number of possible slabs  in the requested data set range. The <b>SlabAllocationBitMapLength</b> of the bitmap returned is (<i>number of slabs</i> / 32) + ((<i>number of slabs</i> MOD 32) &gt; 0 ? 1 : 0).

Slab size is determined by the <b>OptimalUnmapGranularity</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439649">DEVICE_LB_PROVISIONING_DESCRIPTOR</a> returned from an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a> request. The length of the data set range provided should be a multiple of <b>OptimalUnmapGranularity</b>. When the range length is not a multiple of <b>OptimalUnmapGranularity</b>, it is reduced to be a multiple.

If the starting offset in the data set range is not aligned on a slab boundary, a multiple of <b>OptimalUnmapGranularity</b>, the offset will be adjusted to the next boundary. The difference between the requested offset and the adjusted offset is returned in <b>SlabOffsetDeltaInBytes</b>.

If the slab allocation total returned in <b>SlabAllocationBitMapBitCount</b> is not as expected because of data set range alignment or length adjustments, an additional request may be submitted with a data set range modified according to the values in both <b>SlabAllocationBitMapBitCount</b> and <b>SlabOffsetDeltaInBytes</b>. The new range will properly select the slabs left out of the bitmap returned by the previous request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552520">DEVICE_DATA_MANAGEMENT_SET_ACTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552527">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560573">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a>
 

 

