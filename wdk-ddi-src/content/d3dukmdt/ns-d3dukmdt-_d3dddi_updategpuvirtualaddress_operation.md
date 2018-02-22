---
UID: NS:d3dukmdt._D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION
title: "_D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION"
author: windows-driver-content
description: D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION describes a virtual address update operation.
old-location: display\d3dddi_updategpuvirtualaddress_operation.htm
old-project: display
ms.assetid: BCA741A8-2294-43C1-8B9C-3724274D637B
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION structure [Display Devices], _D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION, d3dukmdt/D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION, display.d3dddi_updategpuvirtualaddress_operation, D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dukmdt.h
apiname:
-	D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION
product: Windows
targetos: Windows
req.typenames: D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION
---

# _D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION structure


## -description


<b>D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION</b> describes a virtual address update operation.


## -syntax


````
typedef struct _D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION {
  D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION_TYPE OperationType;
  union {
    struct {
      D3DGPU_VIRTUAL_ADDRESS BaseAddress;
      D3DGPU_SIZE_T          SizeInBytes;
      D3DKMT_HANDLE          hAllocation;
      D3DGPU_SIZE_T          AllocationOffsetInBytes;
      D3DGPU_SIZE_T          AllocationSizeInBytes;
    } Map;
    struct {
      D3DGPU_VIRTUAL_ADDRESS                  BaseAddress;
      D3DGPU_SIZE_T                           SizeInBytes;
      D3DKMT_HANDLE                           hAllocation;
      D3DGPU_SIZE_T                           AllocationOffsetInBytes;
      D3DGPU_SIZE_T                           AllocationSizeInBytes;
      D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE Protection;
      UINT64                                  DriverProtection;
    } MapProtect;
    struct {
      D3DGPU_VIRTUAL_ADDRESS                  BaseAddress;
      D3DGPU_SIZE_T                           SizeInBytes;
      D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE Protection;
    } Unmap;
    struct {
      D3DGPU_VIRTUAL_ADDRESS BaseAddress;
      D3DGPU_SIZE_T          SizeInBytes;
      D3DGPU_VIRTUAL_ADDRESS DestAddress;
    } Copy;
  };
} D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION;
````


## -struct-fields




### -field OperationType


### -field Map

Maps the given virtual address range to the given allocation range. The allocation does not have to be resident at the time of submission or at the time of mapping. The read-write protection is set to the pages. <b>DriverProtection</b> for the pages is set to zero.


### -field Map.BaseAddress

Specifies the <b>BaseAddress</b> of the GPU virtual address range to update. The value is in bytes and must be 4KB aligned.

The entire range from <b>BaseAddress</b> to <b>BaseAddress</b>+<b>SizeInBytes</b> must be in the <i>reserved (zero)</i> or <i>mapped </i>state, or the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updategpuvirtualaddresscb.md">pfnUpdateGpuVirtualAddressCb</a> operation will fail. The virtual address ranges for all operations must belong to a virtual address range which is reserved by the same <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md">pfnReserveGpuVirtualAddressCb</a> call.



### -field Map.SizeInBytes

Specifies the size, in bytes, for the range being updated. The value must be 4KB aligned.


### -field Map.hAllocation

Specifies the allocation the range needs to be mapped to.


### -field Map.AllocationOffsetInBytes

Specifies the offset, in bytes, to the first page in the allocation to map. The value must be 4KB aligned.


### -field Map.AllocationSizeInBytes

Specifies the size of the allocation range to map, in bytes. The value must be 4KB aligned and must be less than <b>Map.SizeInBytes</b>. If this value is zero, <b>Map.SizeInBytes</b> is used.

When this value is than <b>Map.SizeInBytes</b>, <b>Map.SizeInBytes</b> must be a multiple of it. In this case <b>Map.SizeInBytes</b>/<b>Map.AllocationSizeInBytes</b> virtual address ranges will be mapped to the same allocation range. 


### -field MapProtect

Maps the given virtual address range to the given allocation range. The allocation does not have to be resident at the time of submission or at the time of mapping. The page protection is specified in the operation.


### -field MapProtect.BaseAddress

Specifies the <b>BaseAddress</b> of the GPU virtual address range to update. The value is in bytes and must be 4KB aligned.


The entire range from <b>BaseAddress</b> to <b>BaseAddress</b>+<b>SizeInBytes</b> must be in the <i>reserved (zero)</i> or <i>mapped</i> state, or <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updategpuvirtualaddresscb.md">pfnUpdateGpuVirtualAddressCb</a> will fail. The virtual address ranges for all operations must belong to a virtual address range which is reserved by the same <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md">pfnReserveGpuVirtualAddressCb</a> call.



### -field MapProtect.SizeInBytes

Specifies the size, in bytes, for the range being updated. The value must be 4KB aligned.


### -field MapProtect.hAllocation

Specifies the allocation the range needs to be mapped to.


### -field MapProtect.AllocationOffsetInBytes

Specifies the offset, in bytes, to the first page in the allocation to map. The value must be 4KB aligned.


### -field MapProtect.AllocationSizeInBytes

Specifies the size of the allocation range to map, in bytes. The value must be 4KB aligned and must be less than Map.<b>SizeInBytes</b>. If this value is zero, <b>Map.SizeInBytes</b> is used.


When this value is less than <b>Map.SizeInBytes</b>, <b>Map.SizeInBytes</b> must be a multiple of it. In this case <b>Map.SizeInBytes</b>/<b>Map.AllocationSizeInBytes</b> virtual address ranges will be mapped to the same allocation range.


### -field MapProtect.Protection

Specifies API defined protection for the pages.


### -field MapProtect.DriverProtection

Specifies driver specific protection for the pages.


### -field Unmap

Puts the specified virtual address range to the <i>zero</i> state or to the <i>invalid</i> state.


### -field Unmap.BaseAddress

Specifies the <b>BaseAddress</b> of the GPU virtual address range to put back into the <i>zero</i> state. The value is in bytes and must be 4KB aligned.


### -field Unmap.SizeInBytes

Specifies the size, in bytes, for the range to be freed. The value must be 4KB aligned.


### -field Unmap.Protection

Defines is the page table entry state after un-mapping, either <i>Zero</i> or <i>NoAccess</i>. 


### -field Copy

The copy operation copies all mappings from source GPU virtual address range to the destination range. The source and destination ranges are allowed to intersect. Both ranges must belong to a reserved (zero) virtual address range.



#### BaseAddress

Specifies the start virtual address of the source virtual address range. The value is in bytes and must be 4KB aligned.


### -field Copy.SourceAddress

 


### -field Copy.SizeInBytes

Specifies the size, in bytes, for the range being copied. The value must be 4KB aligned.


### -field Copy.DestAddress

Specifies the start virtual address of the destination virtual address range. The value is in bytes and must be 4KB aligned.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md">pfnReserveGpuVirtualAddressCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updategpuvirtualaddresscb.md">pfnUpdateGpuVirtualAddressCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

