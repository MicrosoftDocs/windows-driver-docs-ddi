---
UID: NS:d3dkmthk._D3DKMT_CREATEALLOCATIONFLAGS
title: _D3DKMT_CREATEALLOCATIONFLAGS (d3dkmthk.h)
description: The D3DKMT_CREATEALLOCATIONFLAGS structure identifies how to create an allocation in a call to the D3DKMTCreateAllocation function.
old-location: display\d3dkmt_createallocationflags.htm
ms.assetid: ddcb8222-808b-4dfe-9303-a588b3522ebe
ms.date: 05/10/2018
ms.keywords: D3DKMT_CREATEALLOCATIONFLAGS, D3DKMT_CREATEALLOCATIONFLAGS structure [Display Devices], OpenGL_Structs_0b22984b-feef-4975-b7d9-596427c82b2b.xml, _D3DKMT_CREATEALLOCATIONFLAGS, d3dkmthk/D3DKMT_CREATEALLOCATIONFLAGS, display.d3dkmt_createallocationflags
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- d3dkmthk.h
api_name:
- D3DKMT_CREATEALLOCATIONFLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_CREATEALLOCATIONFLAGS
---

# _D3DKMT_CREATEALLOCATIONFLAGS structure


## -description


The D3DKMT_CREATEALLOCATIONFLAGS structure identifies how to create an allocation in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtcreateallocation">D3DKMTCreateAllocation</a> function.


## -struct-fields




### -field CreateResource

A UINT value that specifies whether to create a device-specific resource.

If you set <b>CreateShared</b>, you must also set <b>CreateResource</b>.

Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).


### -field CreateShared

A UINT value that specifies whether to create a resource shared across all devices. 

If you set <b>CreateShared</b>, you must also set <b>CreateResource</b>.

For more information on using <b>CreateShared</b>, see the Remarks section.

Setting this member is equivalent to setting the second bit of a 32-bit value (0x00000002).


### -field NonSecure

A UINT value that specifies whether to create an allocation that can be opened by any process. If <b>NonSecure</b> is set, secure and non-secure processes can open the allocation.

Setting this member is equivalent to setting the third bit of a 32-bit value (0x00000004).


### -field CreateProtected

This member is reserved and should be set to zero. Setting this member is equivalent to setting the fourth bit of a 32-bit value (0x00000008).

Supported starting with Windows 7.


### -field RestrictSharedAccess

A UINT value that specifies whether to create a resource shared across all devices but with some restrictions.

Setting this member is equivalent to setting the fifth bit of a 32-bit value (0x00000010).

Supported starting with Windows 7.


### -field ExistingSysMem

This member is reserved and should be set to zero. Setting this member is equivalent to setting the sixth bit of a 32-bit value (0x00000020).

Supported starting with Windows 7.


### -field NtSecuritySharing

A UINT value that specifies whether the allocation is shared with an NT handle, meaning that it  does not have a global <b>D3DKMT_HANDLE</b> kernel-mode handle to the resource.

If <b>NtSecuritySharing</b> is set to 1 (<b>TRUE</b>), the allocation is shared using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtshareobjects">D3DKMTShareObjects</a> function but does not have a global <b>D3DKMT_HANDLE</b> handle to the resource.

<div class="alert"><b>Note</b>  If <b>NtSecuritySharing</b> is set to 1,  <b>CreateShared</b>  must be set to 1.</div>
<div> </div>
For more information on using <b>NtSecuritySharing</b>, see the Remarks section.

Setting this member is equivalent to setting the seventh bit of a 32-bit value (0x00000040).

Supported starting with Windows 8.


### -field ReadOnly

A UINT value that specifies whether the allocation can only be read from.

Setting this member is equivalent to setting the eighth bit of a 32-bit value (0x00000080).

Supported starting with Windows 8.


### -field CreateWriteCombined

This member is reserved and should be set to zero. Setting this member is equivalent to setting the seventh bit of a 32-bit value (0x00000100).

Supported starting with Windows 8.


### -field CreateCached

This member is reserved and should be set to zero. Setting this member is equivalent to setting the eighth bit of a 32-bit value (0x00000200).

Supported starting with Windows 8.


### -field SwapChainBackBuffer

This member is reserved and should be set to zero. Setting this member is equivalent to setting the seventh bit of a 32-bit value (0x00000100).

Supported starting with Windows 8.


### -field CrossAdapter

The cross adapter.


### -field OpenCrossAdapter

 
The open cross adapter. Can't be used when allocation is created from the user mode.

### -field PartialSharedCreation

 


### -field WriteWatch

 


### -field StandardAllocation

 


### -field ExistingSection

 


### -field Zeroed

 


### -field Reserved

Supported starting with Windows 8.

This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 26 bits (0xFFFFFFC0) of a 32-bit value to zeros.


## -remarks



Objects to be shared by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtshareobjects">D3DKMTShareObjects</a> function must first be created with the <b>NtSecuritySharing</b> flag value set. This flag value is available in the <b>D3DKMT_CREATEALLOCATIONFLAGS</b>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_createkeyedmutex2_flags">D3DKMT_CREATEKEYEDMUTEX2_FLAGS</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobject_flags">D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</a> structures.

Drivers should follow these guidelines on <b>D3DKMT_CREATEALLOCATIONFLAGS</b> sharing flags:

<ul>
<li>If the allocation is not shared, set both  <b>CreateShared</b> and <b>NtSecuritySharing</b> to 0.</li>
<li>If the allocation is shared with a <b>D3DKMT_HANDLE</b> data type, set <b>CreateShared</b> = 1 and <b>NtSecuritySharing</b> = 0.</li>
<li>If the allocation is shared with an NT handle to the process (and without a global <b>D3DKMT_HANDLE</b> kernel-mode handle to the resource), set <b>CreateShared</b> = 1 and <b>NtSecuritySharing</b> = 1.</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtcreateallocation">D3DKMTCreateAllocation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_createallocation">D3DKMT_CREATEALLOCATION</a>
 

 

