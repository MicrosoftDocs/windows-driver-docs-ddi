---
UID: NS:d3dkmthk._D3DKMT_CREATEKEYEDMUTEX2_FLAGS
title: "_D3DKMT_CREATEKEYEDMUTEX2_FLAGS"
author: windows-driver-content
description: Indicates how a handle to a keyed mutex is specified.
old-location: display\d3dkmt_createkeyedmutex2_flags.htm
ms.assetid: 21c2d262-bf8c-48a3-9801-5c2bd73f0282
ms.date: 05/10/2018
ms.keywords: D3DKMT_CREATEKEYEDMUTEX2_FLAGS, D3DKMT_CREATEKEYEDMUTEX2_FLAGS structure [Display Devices], _D3DKMT_CREATEKEYEDMUTEX2_FLAGS, d3dkmthk/D3DKMT_CREATEKEYEDMUTEX2_FLAGS, display.d3dkmt_createkeyedmutex2_flags
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmthk.h
api_name:
-	D3DKMT_CREATEKEYEDMUTEX2_FLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_CREATEKEYEDMUTEX2_FLAGS
---

# _D3DKMT_CREATEKEYEDMUTEX2_FLAGS structure


## -description


Indicates how a handle to a keyed mutex is specified.


## -struct-fields




### -field NtSecuritySharing

A UINT value that specifies whether the keyed mutex is shared or has a global <b>D3DKMT_HANDLE</b> kernel-mode handle to the resource.

If <b>NtSecuritySharing</b> is set to 1 (<b>TRUE</b>), the keyed mutex is shared using the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780251">D3DKMTShareObjects</a> function but does not have a global <b>D3DKMT_HANDLE</b> handle to the resource. In this case, the process handle to the resource is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439474">D3DKMT_CREATEKEYEDMUTEX2</a>.<b>hKeyedMutex</b> member in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439345">D3DKMTCreateKeyedMutex2</a> function.

If <b>NtSecuritySharing</b> is set to zero (<b>FALSE</b>), the keyed mutex has a global <b>D3DKMT_HANDLE</b> handle to the resource provided by  the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439474">D3DKMT_CREATEKEYEDMUTEX2</a>.<b>hSharedHandle</b> member in a call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh439345">D3DKMTCreateKeyedMutex2</a>.


### -field Reserved

This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of a 32-bit value to zeros.


### -field Value

[in] A member in the union that <b>D3DKMT_CREATEKEYEDMUTEX2_FLAGS</b> contains that can hold a 32-bit value that identifies the keyed mutex  sharing type.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439345">D3DKMTCreateKeyedMutex2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780251">D3DKMTShareObjects</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439474">D3DKMT_CREATEKEYEDMUTEX2</a>
 

 

