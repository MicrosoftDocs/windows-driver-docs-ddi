---
UID: NC:d3dkmddi.DXGKCB_ENUMHANDLECHILDREN
title: DXGKCB_ENUMHANDLECHILDREN (d3dkmddi.h)
description: The DxgkCbEnumHandleChildren function enumerates all of the allocations that are associated with a given resource, one allocation at a time.
old-location: display\dxgkcbenumhandlechildren.htm
ms.assetid: 36307e63-9e94-4441-92c6-fd4293ea8fa9
ms.date: 05/10/2018
ms.keywords: DXGKCB_ENUMHANDLECHILDREN, DXGKCB_ENUMHANDLECHILDREN callback, DpFunctions_9690e256-00e7-4c6e-88cc-d2e1c32580a2.xml, DxgkCbEnumHandleChildren, DxgkCbEnumHandleChildren callback function [Display Devices], d3dkmddi/DxgkCbEnumHandleChildren, display.dxgkcbenumhandlechildren
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- DxgkCbEnumHandleChildren
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKCB_ENUMHANDLECHILDREN callback function


## -description


The <b>DxgkCbEnumHandleChildren</b> function enumerates all of the allocations that are associated with a given resource, one allocation at a time.


## -parameters




### -param 

*pData*

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557528">DXGKARGCB_ENUMHANDLECHILDREN</a> structure that describes the parent resource and the index of the child allocation to retrieve.


## -returns



<i>DxgkCbEnumHandleChildren</i> returns the graphics subsystem-specific handle to the child allocation that the <i>pData</i> parameter describes. To retrieve the device-specific data for the handle, the display miniport driver must call the <a href="https://msdn.microsoft.com/144429e5-34e6-4416-980e-2838e8f9e415">DxgkCbGetHandleData</a> function.

<i>DxgkCbEnumHandleChildren</i> returns a <b>NULL</b> handle if the child-allocation index that the <b>Index</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557528">DXGKARGCB_ENUMHANDLECHILDREN</a> structure supplies exceeds the number of allocations that are associated with the parent resource. If <i>DxgkCbEnumHandleChildren</i> unexpectedly returns a <b>NULL</b> handle, the Microsoft DirectX graphics kernel subsystem was unable to resolve the handle to the parent resource because, for example, of the following possible reasons:

<ul>
<li>An invalid handle was received from the user-mode display driver because of a malicious attack or some other bug. </li>
<li>Allocations had lifetime issues. </li>
</ul>
If a <b>NULL</b> handle is returned unexpectedly, the display miniport driver should fail its currently running DDI function with STATUS_INVALID_HANDLE.




## -remarks



The display miniport driver can call the <b>DxgkCbEnumHandleChildren</b> function in a loop to enumerate all of the allocations that are associated with a resource. If the display miniport driver sets the <b>Index</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557528">DXGKARGCB_ENUMHANDLECHILDREN</a> structure that is pointed to by the <i>pData</i> parameter to 0, <b>DxgkCbEnumHandleChildren</b> returns the first allocation handle; if <b>Index</b> is set to 1, <b>DxgkCbEnumHandleChildren</b> returns the second allocation handle; and so on. If <b>Index</b> is greater than the number of allocations that are associated with the resource, <b>DxgkCbEnumHandleChildren</b> returns <b>NULL</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557528">DXGKARGCB_ENUMHANDLECHILDREN</a>



<a href="https://msdn.microsoft.com/144429e5-34e6-4416-980e-2838e8f9e415">DxgkCbGetHandleData</a>
 

 

