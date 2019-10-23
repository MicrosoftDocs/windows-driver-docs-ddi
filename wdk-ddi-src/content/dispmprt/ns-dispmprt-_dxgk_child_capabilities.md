---
UID: NS:dispmprt._DXGK_CHILD_CAPABILITIES
title: _DXGK_CHILD_CAPABILITIES (dispmprt.h)
description: The DXGK_CHILD_CAPABILITIES structure contains information about the capabilities of an individual child device of a display adapter.
old-location: display\dxgk_child_capabilities.htm
tech.root: display
ms.assetid: 6ab6a505-ad02-4dce-8061-bba13081208a
ms.date: 05/10/2018
ms.keywords: "*PDXGK_CHILD_CAPABILITIES, DXGK_CHILD_CAPABILITIES, DXGK_CHILD_CAPABILITIES structure [Display Devices], DmStructs_886366a4-949a-4171-abcf-e318df848285.xml, PDXGK_CHILD_CAPABILITIES, PDXGK_CHILD_CAPABILITIES structure pointer [Display Devices], _DXGK_CHILD_CAPABILITIES, display.dxgk_child_capabilities, dispmprt/DXGK_CHILD_CAPABILITIES, dispmprt/PDXGK_CHILD_CAPABILITIES"
ms.topic: struct
f1_keywords:
 - "dispmprt/DXGK_CHILD_CAPABILITIES"
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dispmprt.h
api_name:
- DXGK_CHILD_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: DXGK_CHILD_CAPABILITIES, *PDXGK_CHILD_CAPABILITIES
---

# _DXGK_CHILD_CAPABILITIES structure


## -description


The DXGK_CHILD_CAPABILITIES structure contains information about the capabilities of an individual child device of a display adapter.


## -struct-fields




### -field Type


      A union that can contain either video output information or other information in the following members. 
     


### -field Type.VideoOutput

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_video_output_capabilities">DXGK_VIDEO_OUTPUT_CAPABILITIES</a> structure that contains information about a video output. This member is meaningful only if the child device has type <b>TypeVideoOutput</b>.


### -field Type.Other

A structure whose only member must be equal to zero if the child device has type <b>TypeOther</b>.


### -field Type.Other.MustBeZero

A UINT value that must be equal to zero.


### -field Type.IntegratedDisplayChild

Returns the integrated display child specific fields of the child capabilities.


### -field HpdAwareness

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgk_child_device_hpd_awareness">DXGK_CHILD_DEVICE_HPD_AWARENESS</a> enumerator that indicates the child device's level of hot-plug awareness.


## -remarks



The <b>ChildDeviceType</b> member of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a> structure is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ne-dispmprt-_dxgk_child_device_type">DXGK_CHILD_DEVICE_TYPE</a> enumerator that indicates type of the child device: <b>TypeVideoOutput</b> or <b>TypeOther</b>.

If a child device is of type <b>TypeVideoOutput</b>, the <b>Type.VideoOutput</b> member of its DXGK_CHILD_DESCRIPTOR structure is a DXGK_VIDEO_OUTPUT_CAPABILITIES structure.

If a child device is of type <b>TypeOther</b>, then <b>Type.Other.MustBeZero</b> must be set to zero.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_video_output_capabilities">DXGK_VIDEO_OUTPUT_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>
 

 

