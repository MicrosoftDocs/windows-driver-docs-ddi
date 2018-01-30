---
UID: NS:d3dkmthk._D3DKMT_CREATEALLOCATIONFLAGS
title: "_D3DKMT_CREATEALLOCATIONFLAGS"
author: windows-driver-content
description: The D3DKMT_CREATEALLOCATIONFLAGS structure identifies how to create an allocation in a call to the D3DKMTCreateAllocation function.
old-location: display\d3dkmt_createallocationflags.htm
old-project: display
ms.assetid: ddcb8222-808b-4dfe-9303-a588b3522ebe
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_CREATEALLOCATIONFLAGS, D3DKMT_CREATEALLOCATIONFLAGS structure [Display Devices], display.d3dkmt_createallocationflags, OpenGL_Structs_0b22984b-feef-4975-b7d9-596427c82b2b.xml, _D3DKMT_CREATEALLOCATIONFLAGS, d3dkmthk/D3DKMT_CREATEALLOCATIONFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_CREATEALLOCATIONFLAGS
product: Windows
targetos: Windows
req.typenames: D3DKMT_CREATEALLOCATIONFLAGS
---

# _D3DKMT_CREATEALLOCATIONFLAGS structure


## -description


The D3DKMT_CREATEALLOCATIONFLAGS structure identifies how to create an allocation in a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreateallocation.md">D3DKMTCreateAllocation</a> function.


## -syntax


````
typedef struct _D3DKMT_CREATEALLOCATIONFLAGS {
  UINT CreateResource  :1;
  UINT CreateShared  :1;
  UINT NonSecure  :1;
  UINT CreateProtected  :1;
  UINT RestrictSharedAccess  :1;
  UINT ExistingSysMem  :1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  UINT NtSecuritySharing  :1;
  UINT ReadOnly  :1;
  UINT CreateWriteCombined  :1;
  UINT CreateCached  :1;
  UINT SwapChainBackBuffer  :1;
  UINT Reserved  :21;
#else 
  UINT Reserved  :26;
} D3DKMT_CREATEALLOCATIONFLAGS;
````


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

If <b>NtSecuritySharing</b> is set to 1 (<b>TRUE</b>), the allocation is shared using the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtshareobjects.md">D3DKMTShareObjects</a> function but does not have a global <b>D3DKMT_HANDLE</b> handle to the resource.
<div class="alert"><b>Note</b>  If <b>NtSecuritySharing</b> is set to 1,  <b>CreateShared</b>  must be set to 1.</div><div> </div>For more information on using <b>NtSecuritySharing</b>, see the Remarks section.

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

 


### -field OpenCrossAdapter

 


### -field PartialSharedCreation

 


### -field WriteWatch

 


### -field StandardAllocation

 


### -field ExistingSection

 


### -field Zeroed

 


### -field Reserved

This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 22 bits (0xFFFFFC00) of a 32-bit value to zeros.

Supported starting with Windows 8.

This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 26 bits (0xFFFFFFC0) of a 32-bit value to zeros.


## -remarks


Objects to be shared by using the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtshareobjects.md">D3DKMTShareObjects</a> function must first be created with the <b>NtSecuritySharing</b> flag value set. This flag value is available in the <b>D3DKMT_CREATEALLOCATIONFLAGS</b>, <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createkeyedmutex2_flags.md">D3DKMT_CREATEKEYEDMUTEX2_FLAGS</a>, and <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_synchronizationobject_flags.md">D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</a> structures.

Drivers should follow these guidelines on <b>D3DKMT_CREATEALLOCATIONFLAGS</b> sharing flags:
<ul>
<li>If the allocation is not shared, set both  <b>CreateShared</b> and <b>NtSecuritySharing</b> to 0.</li>
<li>If the allocation is shared with a <b>D3DKMT_HANDLE</b> data type, set <b>CreateShared</b> = 1 and <b>NtSecuritySharing</b> = 0.</li>
<li>If the allocation is shared with an NT handle to the process (and without a global <b>D3DKMT_HANDLE</b> kernel-mode handle to the resource), set <b>CreateShared</b> = 1 and <b>NtSecuritySharing</b> = 1.</li>
</ul>


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreateallocation.md">D3DKMTCreateAllocation</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createallocation.md">D3DKMT_CREATEALLOCATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CREATEALLOCATIONFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

