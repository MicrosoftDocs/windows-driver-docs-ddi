---
UID: NC:dispmprt.DXGKDDI_QUERY_DEVICE_DESCRIPTOR
title: DXGKDDI_QUERY_DEVICE_DESCRIPTOR (dispmprt.h)
description: The DxgkDdiQueryDeviceDescriptor function returns a descriptor for a child device of a display adapter or for an external device (typically a monitor) connected to a child device of a display adapter.
old-location: display\dxgkddiquerydevicedescriptor.htm
tech.root: display
ms.assetid: 0dfcc012-9fff-40b6-b71f-da2ca229896c
ms.date: 05/10/2018
ms.keywords: DXGKDDI_QUERY_DEVICE_DESCRIPTOR, DXGKDDI_QUERY_DEVICE_DESCRIPTOR callback, DmFunctions_84688704-46fd-40d6-993e-298c6d3d5dcd.xml, DxgkDdiQueryDeviceDescriptor, DxgkDdiQueryDeviceDescriptor callback function [Display Devices], display.dxgkddiquerydevicedescriptor, dispmprt/DxgkDdiQueryDeviceDescriptor
ms.topic: callback
f1_keywords:
 - "dispmprt/DxgkDdiQueryDeviceDescriptor"
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
- DxgkDdiQueryDeviceDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_QUERY_DEVICE_DESCRIPTOR callback function


## -description


The <i>DxgkDdiQueryDeviceDescriptor</i> function returns a descriptor for a child device of a display adapter or for an external device (typically a monitor) connected to a child device of a display adapter.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param ChildUid [in]

An integer that uniquely identifies the child device. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a> function previously provided this identifier to the display port driver.


### -param DeviceDescriptor [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_dxgk_device_descriptor">DXGK_DEVICE_DESCRIPTOR</a> structure. The caller initializes the <b>DescriptorLength</b> and <b>DescriptorBuffer</b> members. If the child device has a type of <b>TypeVideoOutput</b>, the caller also initializes the <b>DescriptorOffset</b> member. On return, the caller-allocated buffer pointed to by the <b>DescriptorBuffer</b> member receives the descriptor.


## -returns

<i>DxgkDdiQueryDeviceDescriptor </i>returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The function successfully returned the device descriptor. | 
| **STATUS_GRAPHICS_CHILD_DESCRIPTOR_NOT_SUPPORTED** | The (onboard) child device identified by ChildUid does not support a descriptor. | 
| **STATUS_MONITOR_NO_DESCRIPTOR** | The child device identified by ChildUid is connected to a monitor that does not support an EDID descriptor. | 
| **STATUS_MONITOR_NO_MORE_DESCRIPTOR_DATA** | The child device identified by ChildUid is connected to a monitor that does support an EDID descriptor, but the descriptor does not have the EDID extension block specified by the DescriptorOffset and DescriptorLengthmembers of DeviceDescriptor. | 


## -remarks



<i>DxgkDdiQueryDeviceDescriptor</i> must never write more than the number of bytes specified by <i>DeviceDescriptor</i>-><b>DescriptorLength</b>.

If the child device identified by <i>ChildUid</i> has a type of <b>TypeVideoOutput</b>, <i>DxgkDdiQueryDeviceDescriptor</i> returns a portion of the Extended Display Identification Data (EDID) for the monitor connected to the output. <i>DeviceDescriptor</i>-><b>DescriptorOffset</b> specifies the byte-offset into the EDID of the start of the data to be returned.

If the child device identified by <i>ChildUid</i> is not a video output, <i>DxgkDdiQueryDeviceDescriptor</i> returns a generic device descriptor; that is, it fills in the members of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_dxgk_generic_descriptor">DXGK_GENERIC_DESCRIPTOR</a> structure.

The <i>DxgkDdiQueryDeviceDescriptor</i> function can be called several times for one child device. For a child device that has a connected monitor, the display port driver calls <i>DxgkDdiQueryDeviceDescriptor</i> during initialization to obtain the first 128-byte block of a monitor's EDID. Later the monitor class function driver (Monitor.sys) calls <i>DxgkDdiQueryDeviceDescriptor</i> to obtain selected portions (including the first 128-byte block) of that same monitor's EDID.

<i>DxgkDdiQueryDeviceDescriptor</i> should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_dxgk_device_descriptor">DXGK_DEVICE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_query_child_status">DxgkDdiQueryChildStatus</a>
 

 

