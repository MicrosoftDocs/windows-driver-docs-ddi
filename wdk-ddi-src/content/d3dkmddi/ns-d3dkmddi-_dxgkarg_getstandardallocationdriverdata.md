---
UID: NS:d3dkmddi._DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA
title: "_DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA"
author: windows-driver-content
description: The DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA structure describes a standard allocation type.
old-location: display\dxgkarg_getstandardallocationdriverdata.htm
old-project: display
ms.assetid: 4327ba59-bd74-4018-85d2-54a1693c62c1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*INOUT_PDXGKARG_GETSTANDARDALLOCATIONDRIVERDATA, DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA, DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA structure [Display Devices], DmStructs_2ef51052-bc21-4374-9471-c03b2a81b8b3.xml, _DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA, d3dkmddi/DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA, display.dxgkarg_getstandardallocationdriverdata"
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
-	DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA
product: Windows
targetos: Windows
req.typenames: DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA
---

# _DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA structure


## -description


The DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA structure describes a standard allocation type.


## -struct-fields




### -field StandardAllocationType

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff546589">D3DKMDT_STANDARDALLOCATION_TYPE</a>-typed value that identifies the type of standard allocation to describe.


### -field pAllocationPrivateDriverData

[in/out] A pointer to a block of allocation private data that describes the standard allocation type; otherwise, this member is <b>NULL</b>. The allocation private data that the display miniport driver's <a href="https://msdn.microsoft.com/38a9859f-ed9f-41a5-9bf1-c734480499ea">DxgkDdiGetStandardAllocationDriverData</a> function returns depends on the type that the driver requests in <b>StandardAllocationType</b>.


### -field AllocationPrivateDriverDataSize

[out] The size, in bytes, of the allocation private data that <b>pAllocationPrivateDriverData</b> points to. If the driver sets <b>pAllocationPrivateDriverData</b> to <b>NULL</b>, the driver should set <b>AllocationPrivateDriverDataSize</b> to the size of the buffer that the driver requires to describe the given standard allocation type.

If the driver does not use private data for each allocation for standard allocations types, the driver can set <b>AllocationPrivateDriverDataSize</b> to zero. 


### -field pResourcePrivateDriverData

[in/out] A pointer to a block of resource private data that describes the standard allocation type; otherwise, this member is <b>NULL</b>. The resource private data that the display miniport driver's <a href="https://msdn.microsoft.com/38a9859f-ed9f-41a5-9bf1-c734480499ea">DxgkDdiGetStandardAllocationDriverData</a> function returns depends on the type that the driver requests in <b>StandardAllocationType</b>.


### -field ResourcePrivateDriverDataSize

[out] The size, in bytes, of the resource private data that <b>pResourcePrivateDriverData</b> points to. If the driver sets <b>pResourcePrivateDriverData</b> to <b>NULL</b>, the driver should set <b>ResourcePrivateDriverDataSize</b> to the size of the buffer that the driver requires to describe the given standard allocation type.

If the driver does not use private data for each resource for standard allocations types, the driver can set <b>ResourcePrivateDriverDataSize</b> to zero. 


### -field PhysicalAdapterIndex

 




#### - pCreateGdiSurfaceData

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546021">D3DKMDT_GDISURFACEDATA</a> structure, only available if <b>StandardAllocationType</b> specifies D3DKMDT_STANDARDALLOCATION_GDISURFACE.

This member is available beginning with Windows 7.


#### - pCreateShadowSurfaceData

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546168">D3DKMDT_SHADOWSURFACEDATA</a> structure, if <b>StandardAllocationType</b> specifies D3DKMDT_STANDARDALLOCATION_SHADOWSURFACE.


#### - pCreateSharedPrimarySurfaceData

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546177">D3DKMDT_SHAREDPRIMARYSURFACEDATA</a> structure, if <b>StandardAllocationType</b> specifies D3DKMDT_STANDARDALLOCATION_SHAREDPRIMARYSURFACE.


#### - pCreateStagingSurfaceData

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546583">D3DKMDT_STAGINGSURFACEDATA</a> structure, if <b>StandardAllocationType</b> specifies D3DKMDT_STANDARDALLOCATION_STAGINGSURFACE.


## -remarks



If the display miniport driver returns <b>NULL</b> in the <b>pAllocationPrivateDriverData</b> and <b>pResourcePrivateDriverData</b> members, the driver should return the sizes of the buffers that the driver requires in the <b>AllocationPrivateDriverDataSize</b> and <b>ResourcePrivateDriverDataSize</b> members. However, the driver should not change the contents of the standard allocation structure in the union that DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA contains to obtain the required sizes of the buffers. 

Although the driver can set <b>ResourcePrivateDriverDataSize</b> or <b>AllocationPrivateDriverDataSize</b> to zero, the driver cannot set both to zero.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546021">D3DKMDT_GDISURFACEDATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546168">D3DKMDT_SHADOWSURFACEDATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546177">D3DKMDT_SHAREDPRIMARYSURFACEDATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546583">D3DKMDT_STAGINGSURFACEDATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546589">D3DKMDT_STANDARDALLOCATION_TYPE</a>



<a href="https://msdn.microsoft.com/38a9859f-ed9f-41a5-9bf1-c734480499ea">DxgkDdiGetStandardAllocationDriverData</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

