---
UID: NC:dispmprt.DXGKDDI_GET_CHILD_CONTAINER_ID
title: DXGKDDI_GET_CHILD_CONTAINER_ID (dispmprt.h)
description: Queries the container ID for the specified target. Implemented by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers.
old-location: display\dxgkddigetchildcontainerid.htm
tech.root: display
ms.assetid: e7073fb3-0cb7-425e-9ffb-d7eaa963a70f
ms.date: 05/10/2018
keywords: ["DXGKDDI_GET_CHILD_CONTAINER_ID callback function"]
ms.keywords: DXGKDDI_GET_CHILD_CONTAINER_ID, DXGKDDI_GET_CHILD_CONTAINER_ID callback, DxgkDdiGetChildContainerId, DxgkDdiGetChildContainerId callback function [Display Devices], display.dxgkddigetchildcontainerid, dispmprt/DxgkDdiGetChildContainerId
f1_keywords:
 - "dispmprt/DxgkDdiGetChildContainerId"
 - "DxgkDdiGetChildContainerId"
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dispmprt.h
api_name:
- DxgkDdiGetChildContainerId
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_GET_CHILD_CONTAINER_ID callback function


## -description


 Queries the container ID for the specified target. Implemented by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.




### -param ChildUid [in]

A ULONG value that uniquely identifies the child device. The display miniport driver  previously provided this identifier when its  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a> function was called.


### -param ContainerId [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_container_id">DXGK_CHILD_CONTAINER_ID</a> structure. For more information, see the Remarks section.


## -returns



Returns one of the following error codes.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The driver has updated the structure pointed to by the ContainerId parameter with  container ID information obtained from the display hardware.|
|STATUS_MONITOR_NODESCRIPTOR|The driver has accepted the default container ID information provided in the structure pointed to by  ContainerId. **Note:** If the driver returns this status code, it should not modify the structure.|
 

Otherwise the function returns one of the status codes defined in Ntstatus.h.




## -remarks



The operating system calls the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a> function to enumerate the child devices of the display adapter. The operating system then calls the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_device_descriptor">DxgkDdiQueryDeviceDescriptor</a> function for each child device to obtain the  Extended Display Information Data (EDID) for the device. For more information on this procedure, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/enumerating-child-devices-of-a-display-adapter">Enumerating Child Devices of a Display Adapter</a>.

Based on the device's EDID data, the operating system generates a default container ID for the child device. Then, the operating system calls the display miniport driver's <i>DxgkDdiGetChildContainerId</i> function and passes a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_container_id">DXGK_CHILD_CONTAINER_ID</a> structure through the <i>ContainerId</i> parameter. The <b>ContainerId</b> member of this structure contains the default container ID for the child display device.

The display miniport driver can either accept the default container ID or set the <b>ContainerId</b> member to a unique identifier for the device before it returns from the call to <i>DxgkDdiGetChildContainerId</i>.

For more information about Container IDs, see <a href="https://docs.microsoft.com/windows/desktop/com/com-error-codes-4">Container IDs</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_container_id">DXGK_CHILD_CONTAINER_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_device_descriptor">DxgkDdiQueryDeviceDescriptor</a>
 

 

