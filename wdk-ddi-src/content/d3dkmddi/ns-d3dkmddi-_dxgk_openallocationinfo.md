---
UID: NS:d3dkmddi._DXGK_OPENALLOCATIONINFO
title: "_DXGK_OPENALLOCATIONINFO"
author: windows-driver-content
description: The DXGK_OPENALLOCATIONINFO structure contains handles to nondevice-specific and device-specific allocations that the DxgkDdiOpenAllocation function associates.
old-location: display\dxgk_openallocationinfo.htm
old-project: display
ms.assetid: e23b7e4e-e670-4421-aa2f-4389a74a7d6d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_OPENALLOCATIONINFO, DmStructs_e03247bd-d6b8-42df-ac22-79d906d7c852.xml, d3dkmddi/DXGK_OPENALLOCATIONINFO, _DXGK_OPENALLOCATIONINFO, display.dxgk_openallocationinfo, DXGK_OPENALLOCATIONINFO structure [Display Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_OPENALLOCATIONINFO
product: Windows
targetos: Windows
req.typenames: DXGK_OPENALLOCATIONINFO
---

# _DXGK_OPENALLOCATIONINFO structure


## -description


The DXGK_OPENALLOCATIONINFO structure contains handles to nondevice-specific and device-specific allocations that the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_openallocationinfo.md">DxgkDdiOpenAllocation</a> function associates. 


## -syntax


````
typedef struct _DXGK_OPENALLOCATIONINFO {
  D3DKMT_HANDLE hAllocation;
  VOID          *pPrivateDriverData;
  UINT          PrivateDriverDataSize;
  HANDLE        hDeviceSpecificAllocation;
} DXGK_OPENALLOCATIONINFO;
````


## -struct-fields




### -field hAllocation

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the nondevice-specific allocation that the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function created. The Microsoft DirectX graphics kernel subsystem (which is part of <i>Dxgkrnl.sys</i>) assigned this handle for the allocation.


### -field pPrivateDriverData

[in/out] A pointer to a block of private data that is passed between the user-mode display driver and the display miniport driver. This block of private data is the same allocation-specific data that is passed in the <b>pPrivateDriverData</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a> structure in the call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function. The display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_openallocationinfo.md">DxgkDdiOpenAllocation</a> function can modify this block of private data if the <b>Create</b> bit-field flag is set in the <b>Flags</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_openallocation.md">DXGKARG_OPENALLOCATION</a> structure. The user-mode display driver can access modifications to the block of private data.


### -field PrivateDriverDataSize

[in] The size, in bytes, of the block of private data that <b>pPrivateDriverData</b> points to.


### -field hDeviceSpecificAllocation

[out] A handle to the device-specific allocation that corresponds to the non device-specific allocation that <b>hAllocation</b> specifies. The display miniport driver must set <b>hDeviceSpecificAllocation</b> to a handle value that it can use to refer to its private tracking structure for the allocation.


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_openallocation.md">DXGKARG_OPENALLOCATION</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_openallocationinfo.md">DxgkDdiOpenAllocation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_OPENALLOCATIONINFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

