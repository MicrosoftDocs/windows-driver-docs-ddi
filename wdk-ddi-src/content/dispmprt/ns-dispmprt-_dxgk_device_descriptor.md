---
UID: NS:dispmprt._DXGK_DEVICE_DESCRIPTOR
title: "_DXGK_DEVICE_DESCRIPTOR"
author: windows-driver-content
description: The DXGK_DEVICE_DESCRIPTOR structure is used by the display port driver to request that the display miniport driver return all or a portion of a monitor's Extended Display Identification Data (EDID).
old-location: display\dxgk_device_descriptor.htm
old-project: display
ms.assetid: b6d89426-54d3-4f90-8687-c60e515b4d62
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDXGK_DEVICE_DESCRIPTOR, DXGK_DEVICE_DESCRIPTOR, DXGK_DEVICE_DESCRIPTOR structure [Display Devices], DmStructs_d66c7175-e264-49f4-94ce-f4a92a678010.xml, PDXGK_DEVICE_DESCRIPTOR, PDXGK_DEVICE_DESCRIPTOR structure pointer [Display Devices], _DXGK_DEVICE_DESCRIPTOR, display.dxgk_device_descriptor, dispmprt/DXGK_DEVICE_DESCRIPTOR, dispmprt/PDXGK_DEVICE_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dispmprt.h
api_name:
-	DXGK_DEVICE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: DXGK_DEVICE_DESCRIPTOR, *PDXGK_DEVICE_DESCRIPTOR
---

# _DXGK_DEVICE_DESCRIPTOR structure


## -description


The DXGK_DEVICE_DESCRIPTOR structure is used by the display port driver to request that the display miniport driver return all or a portion of a monitor's Extended Display Identification Data (EDID).


## -struct-fields




### -field DescriptorOffset

An integer that indicates an offset, in bytes, into the EDID. This member specifies the beginning of the requested data. 


### -field DescriptorLength

An integer that indicates the length, in bytes, of the buffer pointed to by <b>DescriptorBuffer</b>.


### -field DescriptorBuffer

A pointer to a buffer that receives all or a portion of the monitor's EDID. This buffer is allocated by the display port driver and filled in by the display miniport driver. The display miniport driver must not write more than <b>DescriptorLength</b> bytes to this buffer.


## -remarks



The display port driver passes a DXGK_DEVICE_DESCRIPTOR structure to <a href="https://msdn.microsoft.com/0dfcc012-9fff-40b6-b71f-da2ca229896c">DxgkDdiQueryDeviceDescriptor</a> to request that the display miniport driver return all or a portion of a monitor's EDID. The desired portion of the EDID is specified by the <b>DescriptorOffset</b> and <b>DescriptorLength</b> members. For example, to request 256 bytes, starting at an offset of 128 bytes into a monitor's EDID, the display port driver would set <b>DescriptorOffset</b> to 128, and <b>DescriptorLength</b> to 256.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561108">DXGK_GENERIC_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>



<a href="https://msdn.microsoft.com/0dfcc012-9fff-40b6-b71f-da2ca229896c">DxgkDdiQueryDeviceDescriptor</a>
 

 

