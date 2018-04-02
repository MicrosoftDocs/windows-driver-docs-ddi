---
UID: NS:d3dukmdt.D3DDDI_MAPGPUVIRTUALADDRESS
title: D3DDDI_MAPGPUVIRTUALADDRESS
author: windows-driver-content
description: D3DDDI_MAPGPUVIRTUALADDRESS is used with pfnMapGpuVirtualAddressCb to map a graphics processing unit (GPU) virtual address ranges to a specific allocation range or to put it to the Invalid or Zero state.
old-location: display\d3dddi_mapgpuvirtualaddress.htm
old-project: display
ms.assetid: A23F5847-0DA9-4F3F-B1C1-DACCA35DBC53
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDI_MAPGPUVIRTUALADDRESS, D3DDDI_MAPGPUVIRTUALADDRESS structure [Display Devices], Execute, NoAccess, Write, Zero, d3dukmdt/D3DDDI_MAPGPUVIRTUALADDRESS, display.d3dddi_mapgpuvirtualaddress
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dukmdt.h
api_name:
-	D3DDDI_MAPGPUVIRTUALADDRESS
product: Windows
targetos: Windows
req.typenames: D3DDDI_MAPGPUVIRTUALADDRESS
---

# D3DDDI_MAPGPUVIRTUALADDRESS structure


## -description


<b>D3DDDI_MAPGPUVIRTUALADDRESS</b> is used with <a href="https://msdn.microsoft.com/DA67A98C-BE9C-412D-9382-CAC5B05FEE3B">pfnMapGpuVirtualAddressCb</a> to map a graphics processing unit (GPU) virtual address ranges to a specific allocation range or to put it to the <i>Invalid</i> or <i>Zero</i> state.


## -struct-fields




### -field hPagingQueue

A handle for the device paging queue, used for the operation.


### -field BaseAddress

(Optional) If non-<b>NULL</b>, the video memory manager will attempt to use this address as the base address for the mapping. If the range from <b>BaseAddress</b> to <b>BaseAddress</b>+<b>Size</b> isn’t free, it must belong to a range, previously obtained by calling <a href="https://msdn.microsoft.com/CEDE03E1-4B0D-4839-B7D6-0826CC103C5E">pfnReserveGpuVirtualAddressCb</a> or <a href="https://msdn.microsoft.com/DA67A98C-BE9C-412D-9382-CAC5B05FEE3B">pfnMapGpuVirtualAddressCb</a>. 
The <b>BaseAddress</b> value is in bytes and must be aligned to CPU page boundary.
If <b>NULL</b> is specified, the video memory manager will pick the base address for the allocation within the specified <b>MinimumAddress</b> and <b>MaximumAddress</b>.


### -field MinimumAddress

(Optional) Specifies the minimum GPU virtual address to consider for the mapped range. 
The <b>MinimumAddress</b> value is in bytes and must be aligned to 4KB page. 
This parameter is ignored when <b>BaseAddress</b> != <b>NULL.</b>


### -field MaximumAddress


(Optional) Specifies the maximum GPU virtual address to consider for the mapped range. the video memory manager will guarantee that <b>BaseAddress</b>+<b>Size</b> &lt;= <b>MaximumAddress</b>. If this is set to <b>NULL</b> the video memory manager will not apply any limit.
The <b>MaximumAddress</b> value is in bytes and must be aligned to the 4KB page.
This parameter is ignored when <b>BaseAddress</b> != NULL.



### -field hAllocation

Handle to the allocation being mapped into the GPU virtual address space. Must be <b>NULL</b> when <b>Protection.NoAccess</b> or <b>Protection.Zero</b> is specified.


### -field OffsetInPages

Specifies the offset, in 4KB, to the starting page within the specified allocation that must be mapped.


### -field SizeInPages

Specifies the size of the range to map in 4KB pages.


### -field Protection


<a href="https://msdn.microsoft.com/library/windows/hardware/dn906319">D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE</a> structure that specifies the protection on the GPU virtual address that is mapped.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="Write"></a><a id="write"></a><a id="WRITE"></a><dl>
<dt><b>Write</b></dt>
</dl>
</td>
<td width="60%">
The pages will be allowed read-write access.

</td>
</tr>
<tr>
<td width="40%"><a id="Execute"></a><a id="execute"></a><a id="EXECUTE"></a><dl>
<dt><b>Execute</b></dt>
</dl>
</td>
<td width="60%">
The pages will be allowed the execute access.

</td>
</tr>
<tr>
<td width="40%"><a id="NoAccess"></a><a id="noaccess"></a><a id="NOACCESS"></a><dl>
<dt><b>NoAccess</b></dt>
</dl>
</td>
<td width="60%">
The pages will be put to the invalid state (<b>hAllocation</b> must be <b>NULL</b>).

</td>
</tr>
<tr>
<td width="40%"><a id="Zero"></a><a id="zero"></a><a id="ZERO"></a><dl>
<dt><b>Zero</b></dt>
</dl>
</td>
<td width="60%">
The pages will be put to the Zero state (<b>hAllocation</b> must be <b>NULL</b>).In this state reads will return zero and writes will be discarded.


</td>
</tr>
</table>
 


### -field DriverProtection

Specifies a driver specific 64bits protection value associated with the VA range being allocated. The specified driver protection will be used in call to <a href="https://msdn.microsoft.com/08328e82-d1cc-4c50-bc96-7382232676ab">DxgkDdiUpdatePageTable</a> for page table entries corresponding to this virtual address range.


### -field Reserved0

This member is reserved and should be set to zero.


### -field Reserved1

This member is reserved and should be set to zero.


### -field VirtualAddress

The virtual address assigned to the allocation.


### -field PagingFenceValue

Represents the device paging fence value that the video memory manager will signal when the map operation completes on the GPU.
The user mode driver must ensure that this fence is retired or explicitly wait on either the CPU or the GPU on that fence before allowing the GPU to access the mapped range or an unrecoverable fault may occur.
A zero fence value might be returned, meaning that the operation is already completed.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906319">D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE</a>



<a href="https://msdn.microsoft.com/08328e82-d1cc-4c50-bc96-7382232676ab">DxgkDdiUpdatePageTable</a>



<a href="https://msdn.microsoft.com/DA67A98C-BE9C-412D-9382-CAC5B05FEE3B">pfnMapGpuVirtualAddressCb</a>



<a href="https://msdn.microsoft.com/CEDE03E1-4B0D-4839-B7D6-0826CC103C5E">pfnReserveGpuVirtualAddressCb</a>
 

 

