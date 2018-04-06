---
UID: NS:d3dkmddi._DXGK_OPENALLOCATIONINFO
title: "_DXGK_OPENALLOCATIONINFO"
author: windows-driver-content
description: The DXGK_OPENALLOCATIONINFO structure contains handles to nondevice-specific and device-specific allocations that the DxgkDdiOpenAllocation function associates.
old-location: display\dxgk_openallocationinfo.htm
old-project: display
ms.assetid: e23b7e4e-e670-4421-aa2f-4389a74a7d6d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_OPENALLOCATIONINFO, DXGK_OPENALLOCATIONINFO structure [Display Devices], DmStructs_e03247bd-d6b8-42df-ac22-79d906d7c852.xml, _DXGK_OPENALLOCATIONINFO, d3dkmddi/DXGK_OPENALLOCATIONINFO, display.dxgk_openallocationinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_OPENALLOCATIONINFO
product:
- Windows
targetos: Windows
req.typenames: DXGK_OPENALLOCATIONINFO
---

# _DXGK_OPENALLOCATIONINFO structure


## -description


The DXGK_OPENALLOCATIONINFO structure contains handles to nondevice-specific and device-specific allocations that the <a href="https://msdn.microsoft.com/551154d7-950d-40e5-810b-8d803c1731ca">DxgkDdiOpenAllocation</a> function associates. 


## -struct-fields




### -field hAllocation

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the nondevice-specific allocation that the <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function created. The Microsoft DirectX graphics kernel subsystem (which is part of <i>Dxgkrnl.sys</i>) assigned this handle for the allocation.


### -field pPrivateDriverData

[in/out] A pointer to a block of private data that is passed between the user-mode display driver and the display miniport driver. This block of private data is the same allocation-specific data that is passed in the <b>pPrivateDriverData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560960">DXGK_ALLOCATIONINFO</a> structure in the call to the <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function. The display miniport driver's <a href="https://msdn.microsoft.com/551154d7-950d-40e5-810b-8d803c1731ca">DxgkDdiOpenAllocation</a> function can modify this block of private data if the <b>Create</b> bit-field flag is set in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557609">DXGKARG_OPENALLOCATION</a> structure. The user-mode display driver can access modifications to the block of private data.


### -field PrivateDriverDataSize

[in] The size, in bytes, of the block of private data that <b>pPrivateDriverData</b> points to.


### -field hDeviceSpecificAllocation

[out] A handle to the device-specific allocation that corresponds to the non device-specific allocation that <b>hAllocation</b> specifies. The display miniport driver must set <b>hDeviceSpecificAllocation</b> to a handle value that it can use to refer to its private tracking structure for the allocation.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557609">DXGKARG_OPENALLOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560960">DXGK_ALLOCATIONINFO</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>



<a href="https://msdn.microsoft.com/551154d7-950d-40e5-810b-8d803c1731ca">DxgkDdiOpenAllocation</a>
 

 

