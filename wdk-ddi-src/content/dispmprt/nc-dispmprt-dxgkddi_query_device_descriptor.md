---
UID: NC:dispmprt.DXGKDDI_QUERY_DEVICE_DESCRIPTOR
title: DXGKDDI_QUERY_DEVICE_DESCRIPTOR
author: windows-driver-content
description: The DxgkDdiQueryDeviceDescriptor function returns a descriptor for a child device of a display adapter or for an external device (typically a monitor) connected to a child device of a display adapter.
old-location: display\dxgkddiquerydevicedescriptor.htm
old-project: display
ms.assetid: 0dfcc012-9fff-40b6-b71f-da2ca229896c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddiquerydevicedescriptor, DxgkDdiQueryDeviceDescriptor callback function [Display Devices], DxgkDdiQueryDeviceDescriptor, DXGKDDI_QUERY_DEVICE_DESCRIPTOR, DXGKDDI_QUERY_DEVICE_DESCRIPTOR, dispmprt/DxgkDdiQueryDeviceDescriptor, DmFunctions_84688704-46fd-40d6-993e-298c6d3d5dcd.xml
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
-	UserDefined
apilocation:
-	dispmprt.h
apiname:
-	DxgkDdiQueryDeviceDescriptor
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_QUERY_DEVICE_DESCRIPTOR callback


## -description


The <i>DxgkDdiQueryDeviceDescriptor</i> function returns a descriptor for a child device of a display adapter or for an external device (typically a monitor) connected to a child device of a display adapter.


## -prototype


````
DXGKDDI_QUERY_DEVICE_DESCRIPTOR DxgkDdiQueryDeviceDescriptor;

NTSTATUS DxgkDdiQueryDeviceDescriptor(
  _In_    const PVOID                   MiniportDeviceContext,
  _In_          ULONG                   ChildUid,
  _Inout_       PDXGK_DEVICE_DESCRIPTOR DeviceDescriptor
)
{ ... }
````


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param ChildUid [in]

An integer that uniquely identifies the child device. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a> function previously provided this identifier to the display port driver.


### -param DeviceDescriptor [in, out]

A pointer to a <a href="..\dispmprt\ns-dispmprt-_dxgk_device_descriptor.md">DXGK_DEVICE_DESCRIPTOR</a> structure. The caller initializes the <b>DescriptorLength</b> and <b>DescriptorBuffer</b> members. If the child device has a type of <b>TypeVideoOutput</b>, the caller also initializes the <b>DescriptorOffset</b> member. On return, the caller-allocated buffer pointed to by the <b>DescriptorBuffer</b> member receives the descriptor.


## -returns


<i>DxgkDdiQueryDeviceDescriptor </i>returns one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The function successfully returned the device descriptor.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_CHILD_DESCRIPTOR_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The (onboard) child device identified by <i>ChildUid</i> does not support a descriptor.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MONITOR_NO_DESCRIPTOR</b></dt>
</dl>
</td>
<td width="60%">
The child device identified by <i>ChildUid</i> is connected to a monitor that does not support an EDID descriptor.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MONITOR_NO_MORE_DESCRIPTOR_DATA</b></dt>
</dl>
</td>
<td width="60%">
The child device identified by <i>ChildUid</i> is connected to a monitor that does support an EDID descriptor, but the descriptor does not have the EDID extension block specified by the <b>DescriptorOffset</b> and <b>DescriptorLength</b> members of <i>DeviceDescriptor</i>.

</td>
</tr>
</table> 



## -remarks


<i>DxgkDdiQueryDeviceDescriptor</i> must never write more than the number of bytes specified by <i>DeviceDescriptor</i>-&gt;<b>DescriptorLength</b>.

If the child device identified by <i>ChildUid</i> has a type of <b>TypeVideoOutput</b>, <i>DxgkDdiQueryDeviceDescriptor</i> returns a portion of the Extended Display Identification Data (EDID) for the monitor connected to the output. <i>DeviceDescriptor</i>-&gt;<b>DescriptorOffset</b> specifies the byte-offset into the EDID of the start of the data to be returned.

If the child device identified by <i>ChildUid</i> is not a video output, <i>DxgkDdiQueryDeviceDescriptor</i> returns a generic device descriptor; that is, it fills in the members of a <a href="..\dispmprt\ns-dispmprt-_dxgk_generic_descriptor.md">DXGK_GENERIC_DESCRIPTOR</a> structure.

The <i>DxgkDdiQueryDeviceDescriptor</i> function can be called several times for one child device. For a child device that has a connected monitor, the display port driver calls <i>DxgkDdiQueryDeviceDescriptor</i> during initialization to obtain the first 128-byte block of a monitor's EDID. Later the monitor class function driver (Monitor.sys) calls <i>DxgkDdiQueryDeviceDescriptor</i> to obtain selected portions (including the first 128-byte block) of that same monitor's EDID.

<i>DxgkDdiQueryDeviceDescriptor</i> should be made pageable.



## -see-also

<a href="..\dispmprt\ns-dispmprt-_dxgk_device_descriptor.md">DXGK_DEVICE_DESCRIPTOR</a>

<a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_status.md">DxgkDdiQueryChildStatus</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_QUERY_DEVICE_DESCRIPTOR callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

