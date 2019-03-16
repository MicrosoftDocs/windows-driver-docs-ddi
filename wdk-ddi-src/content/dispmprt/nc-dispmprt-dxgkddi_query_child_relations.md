---
UID: NC:dispmprt.DXGKDDI_QUERY_CHILD_RELATIONS
title: DXGKDDI_QUERY_CHILD_RELATIONS (dispmprt.h)
description: The DxgkDdiQueryChildRelations function enumerates the child devices of a display adapter.
old-location: display\dxgkddiquerychildrelations.htm
tech.root: display
ms.assetid: eb1a0df0-6239-4d82-8477-7dd015f80b6e
ms.date: 05/10/2018
ms.keywords: DXGKDDI_QUERY_CHILD_RELATIONS, DXGKDDI_QUERY_CHILD_RELATIONS callback, DmFunctions_783a9c6c-f6ac-4949-87f0-674dae768d36.xml, DxgkDdiQueryChildRelations, DxgkDdiQueryChildRelations callback function [Display Devices], display.dxgkddiquerychildrelations, dispmprt/DxgkDdiQueryChildRelations
ms.topic: callback
req.header: dispmprt.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dispmprt.h
api_name:
- DxgkDdiQueryChildRelations
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_QUERY_CHILD_RELATIONS callback function


## -description


The <i>DxgkDdiQueryChildRelations</i> function enumerates the child devices of a display adapter.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem. 


### -param ChildRelations [in, out]

A pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a> structures allocated and zeroed by the caller. The number of elements in the array is one greater than the value returned by <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a> in the <i>NumberOfChildren</i> parameter. <i>DxgkDdiQueryChildRelations</i> must fill in all but the last structure in the array with information that describes the child devices of the display adapter. The last structure in the array must remain zeroed.


### -param ChildRelationsSize [in]

The total size, in bytes, of the <i>ChildRelations</i> array including the zeroed structure at the end.


## -returns



<i>DxgkDdiQueryChildRelations</i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



All child devices of the display adapter are onboard; monitors and other external devices that connect to the display adapter are not considered child devices.

The display miniport driver must fill in an array of DXGK_CHILD_DESCRIPTOR structures, one for each of the display adapter's children. The array must contain DXGK_CHILD_DESCRIPTOR structures for all current child devices and all potential child devices. For example, if docking a portable computer will result in new video outputs becoming available, those video outputs must have descriptors in the array, even if they are not currently available.

The <i>DxgkDdiQueryChildRelations</i> function should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561010">DXGK_CHILD_STATUS</a>



<a href="https://msdn.microsoft.com/478e0c52-4324-4062-8e1e-381808b0f481">DxgkDdiQueryChildStatus</a>



<a href="https://msdn.microsoft.com/0dfcc012-9fff-40b6-b71f-da2ca229896c">DxgkDdiQueryDeviceDescriptor</a>
 

 

