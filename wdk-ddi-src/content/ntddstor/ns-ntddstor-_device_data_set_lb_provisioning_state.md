---
UID: NS:ntddstor._DEVICE_DATA_SET_LB_PROVISIONING_STATE
title: "_DEVICE_DATA_SET_LB_PROVISIONING_STATE"
author: windows-driver-content
description: The DEVICE_DATA_SET_LB_PROVISIONING_STATE structure is returned by an IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request when requesting logical block provisioning information for a data set range.
old-location: storage\device_data_set_lb_provisioning_state.htm
old-project: storage
ms.assetid: 99FBD363-0999-4AEE-A222-69C0FB71D248
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "_DEVICE_DATA_SET_LB_PROVISIONING_STATE, ntddstor/PDEVICE_DATA_SET_LB_PROVISIONING_STATE, DEVICE_DATA_SET_LB_PROVISIONING_STATE, storage.device_data_set_lb_provisioning_state, PDEVICE_DATA_SET_LB_PROVISIONING_STATE structure pointer [Storage Devices], DEVICE_DATA_SET_LB_PROVISIONING_STATE structure [Storage Devices], *PDEVICE_DATA_SET_LB_PROVISIONING_STATE, PDEVICE_DATA_SET_LB_PROVISIONING_STATE, ntddstor/DEVICE_DATA_SET_LB_PROVISIONING_STATE"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddstor.h
apiname:
-	DEVICE_DATA_SET_LB_PROVISIONING_STATE
product: Windows
targetos: Windows
req.typenames: DEVICE_DATA_SET_LB_PROVISIONING_STATE, *PDEVICE_DATA_SET_LB_PROVISIONING_STATE
---

# _DEVICE_DATA_SET_LB_PROVISIONING_STATE structure


## -description


The <b>DEVICE_DATA_SET_LB_PROVISIONING_STATE</b> structure is returned by an  <a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> request when requesting logical block  provisioning information for a data set range.


## -syntax


````
typedef struct _DEVICE_DATA_SET_LB_PROVISIONING_STATE {
  ULONG     Size;
  ULONG     Version;
  ULONGLONG SlabSizeInBytes;
  ULONG     SlabOffsetDeltaInBytes;
  ULONG     SlabAllocationBitMapBitCount;
  ULONG     SlabAllocationBitMapLength;
  ULONG     SlabAllocationBitMap[ANYSIZE_ARRAY];
} DEVICE_DATA_SET_LB_PROVISIONING_STATE, *PDEVICE_DATA_SET_LB_PROVISIONING_STATE;
````


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



Provisioning state information is returned when the <b>Action</b> member of <a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes.md">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> is set to <b>DeviceDsmAction_Allocation</b>. The caller should include only one data set range in the system buffer at <b>DataSetRangesOffset</b>.

On return, the system buffer contains a <a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes_output.md">DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUPUT</a> structure followed by the <b>DEVICE_DATA_SET_LB_PROVISIONING_STATE</b> structure. The <b>DEVICE_DATA_SET_LB_PROVISIONING_STATE</b> structure begins at an offset from the beginning of the system buffer specified by <b>OutputBlockOffset</b> in <b>DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUPUT</b>.

Each bit in the allocation bitmap represents a slab mapping within the data set range requested. The bits correspond directly to the slabs in the data set range. This means that bit 0 in the bitmap marks the first slab in the range. A slab is mapped if the bit value = 1 and unmapped if the bit value = 0.

Space for <b>SlabAllocationBitMap</b> should be allocated based on the number of possible slabs  in the requested data set range. The <b>SlabAllocationBitMapLength</b> of the bitmap returned is (<i>number of slabs</i> / 32) + ((<i>number of slabs</i> MOD 32) &gt; 0 ? 1 : 0).

Slab size is determined by the <b>OptimalUnmapGranularity</b> member of <a href="..\ntddstor\ns-ntddstor-_device_lb_provisioning_descriptor.md">DEVICE_LB_PROVISIONING_DESCRIPTOR</a> returned from an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request. The length of the data set range provided should be a multiple of <b>OptimalUnmapGranularity</b>. When the range length is not a multiple of <b>OptimalUnmapGranularity</b>, it is reduced to be a multiple.

If the starting offset in the data set range is not aligned on a slab boundary, a multiple of <b>OptimalUnmapGranularity</b>, the offset will be adjusted to the next boundary. The difference between the requested offset and the adjusted offset is returned in <b>SlabOffsetDeltaInBytes</b>.

If the slab allocation total returned in <b>SlabAllocationBitMapBitCount</b> is not as expected because of data set range alignment or length adjustments, an additional request may be submitted with a data set range modified according to the values in both <b>SlabAllocationBitMapBitCount</b> and <b>SlabOffsetDeltaInBytes</b>. The new range will properly select the slabs left out of the bitmap returned by the previous request.




## -see-also

<a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes.md">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552520">DEVICE_DATA_MANAGEMENT_SET_ACTION</a>



<a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a>



<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DEVICE_DATA_SET_LB_PROVISIONING_STATE structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

