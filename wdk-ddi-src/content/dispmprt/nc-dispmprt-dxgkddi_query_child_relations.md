---
UID: NC:dispmprt.DXGKDDI_QUERY_CHILD_RELATIONS
title: DXGKDDI_QUERY_CHILD_RELATIONS
author: windows-driver-content
description: The DxgkDdiQueryChildRelations function enumerates the child devices of a display adapter.
old-location: display\dxgkddiquerychildrelations.htm
old-project: display
ms.assetid: eb1a0df0-6239-4d82-8477-7dd015f80b6e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SYMBOL_INFO_EX, *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiQueryChildRelations
req.alt-loc: dispmprt.h
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
req.typenames: *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
---

# DXGKDDI_QUERY_CHILD_RELATIONS callback



## -description
The <i>DxgkDdiQueryChildRelations</i> function enumerates the child devices of a display adapter.



## -prototype

````
DXGKDDI_QUERY_CHILD_RELATIONS DxgkDdiQueryChildRelations;

NTSTATUS DxgkDdiQueryChildRelations(
  _In_    const PVOID                  MiniportDeviceContext,
  _Inout_       PDXGK_CHILD_DESCRIPTOR ChildRelations,
  _In_          ULONG                  ChildRelationsSize
)
{ ... }
````


## -parameters

### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem. 


### -param ChildRelations [in, out]

A pointer to an array of <a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a> structures allocated and zeroed by the caller. The number of elements in the array is one greater than the value returned by <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> in the <i>NumberOfChildren</i> parameter. <i>DxgkDdiQueryChildRelations</i> must fill in all but the last structure in the array with information that describes the child devices of the display adapter. The last structure in the array must remain zeroed.


### -param ChildRelationsSize [in]

The total size, in bytes, of the <i>ChildRelations</i> array including the zeroed structure at the end.


## -returns
<i>DxgkDdiQueryChildRelations</i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.


## -remarks
All child devices of the display adapter are onboard; monitors and other external devices that connect to the display adapter are not considered child devices.

The display miniport driver must fill in an array of DXGK_CHILD_DESCRIPTOR structures, one for each of the display adapter's children. The array must contain DXGK_CHILD_DESCRIPTOR structures for all current child devices and all potential child devices. For example, if docking a portable computer will result in new video outputs becoming available, those video outputs must have descriptors in the array, even if they are not currently available.

The <i>DxgkDdiQueryChildRelations</i> function should be made pageable.


## -see-also
<dl>
<dt>
<a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\dispmprt\ns-dispmprt-_dxgk_child_status.md">DXGK_CHILD_STATUS</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_status.md">DxgkDdiQueryChildStatus</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_device_descriptor.md">DxgkDdiQueryDeviceDescriptor</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_QUERY_CHILD_RELATIONS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

