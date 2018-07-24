---
UID: NS:dispmprt._DXGK_CHILD_CONTAINER_ID
title: "_DXGK_CHILD_CONTAINER_ID"
author: windows-driver-content
description: Contains the container ID for a child device that is connected to a display adapter.
old-location: display\dxgk_child_container_id.htm
tech.root: display
ms.assetid: 9573f6e9-80a6-4390-b2ab-4543e3b1f5f4
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: "*PDXGK_CHILD_CONTAINER_ID, DXGK_CHILD_CONTAINER_ID, DXGK_CHILD_CONTAINER_ID structure [Display Devices], PDXGK_CHILD_CONTAINER_ID, PDXGK_CHILD_CONTAINER_ID structure pointer [Display Devices], _DXGK_CHILD_CONTAINER_ID, display.dxgk_child_container_id, dispmprt/DXGK_CHILD_CONTAINER_ID, dispmprt/PDXGK_CHILD_CONTAINER_ID"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dispmprt.h
api_name:
-	DXGK_CHILD_CONTAINER_ID
product:
- Windows
targetos: Windows
req.typenames: DXGK_CHILD_CONTAINER_ID, *PDXGK_CHILD_CONTAINER_ID
---

# _DXGK_CHILD_CONTAINER_ID structure


## -description


Contains the container ID for a child device that is connected to a display adapter.


## -struct-fields




### -field ContainerId

The container ID for the child device. For more information, see the Remarks section.


### -field EldInfo

This structure contains the information that the operating system used to generate the container ID for the child device.


### -field EldInfo.PortId

A ULONG64 value that contains the port ID for the child device. The operating system created this ID based on the name of the child device.


### -field EldInfo.ManufacturerName

A USHORT value that contains the manufacturer's name. The operating system obtains this data from the child device's descriptor.


### -field EldInfo.ProductCode

A USHORT value that contains the manufacturer's product code for the child device. The operating system obtains this data from the child device's descriptor.


## -remarks



The operating system calls the display miniport driver's <a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a> function to enumerate the child devices of the display adapter. The operating system then calls the display miniport driver's <a href="https://msdn.microsoft.com/0dfcc012-9fff-40b6-b71f-da2ca229896c">DxgkDdiQueryDeviceDescriptor</a> function for each child device to obtain the  Extended Display Information Data (EDID) for the device. For more information on this procedure, see <a href="https://msdn.microsoft.com/3bec2117-aef4-41fc-b88a-0081c7c9fe3d">Enumerating Child Devices of a Display Adapter</a>.

Based on the device's EDID data, the operating system generates a default container ID for the child device. Then, the operating system calls the display miniport driver's <a href="https://msdn.microsoft.com/e7073fb3-0cb7-425e-9ffb-d7eaa963a70f">DxgkDdiGetChildContainerId</a> function and passes a pointer to a <b>DXGK_CHILD_CONTAINER_ID</b> structure through the <i>ContainerId</i> parameter. The <b>ContainerId</b> member of this structure contains the default container ID for the child display device.

The display miniport driver can either accept the default container ID because the display hardware has no container ID coded into the firmware, or it can set the <b>ContainerId</b> member to a unique identifier obtained from the display hardware device before it returns from the call to <a href="https://msdn.microsoft.com/e7073fb3-0cb7-425e-9ffb-d7eaa963a70f">DxgkDdiGetChildContainerId</a>.

For more information about Container IDs, see <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/dd542646">Container IDs</a>.




## -see-also




<a href="https://msdn.microsoft.com/e7073fb3-0cb7-425e-9ffb-d7eaa963a70f">DxgkDdiGetChildContainerId</a>



<a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>



<a href="https://msdn.microsoft.com/0dfcc012-9fff-40b6-b71f-da2ca229896c">DxgkDdiQueryDeviceDescriptor</a>
 

 

