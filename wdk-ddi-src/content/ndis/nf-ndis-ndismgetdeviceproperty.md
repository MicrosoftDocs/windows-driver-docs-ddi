---
UID: NF:ndis.NdisMGetDeviceProperty
title: NdisMGetDeviceProperty function (ndis.h)
description: The NdisMGetDeviceProperty function retrieves device objects required to set up communication with a miniport driver through a bus driver.
old-location: netvista\ndismgetdeviceproperty.htm
tech.root: netvista
ms.assetid: caef96b6-1b94-475d-9f78-66ae6d6ac979
ms.date: 05/02/2018
keywords: ["NdisMGetDeviceProperty function"]
ms.keywords: NdisMGetDeviceProperty, NdisMGetDeviceProperty function [Network Drivers Starting with Windows Vista], miniport_ndis_functions_ref_849a967a-d488-4440-a9b5-9c7fbc247acd.xml, ndis/NdisMGetDeviceProperty, netvista.ndismgetdeviceproperty
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 5.1, and NDIS 6.0 and later. For NDIS 5.1 drivers, see    NdisMGetDeviceProperty (NDIS   5.1).
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMGetDeviceProperty
 - ndis/NdisMGetDeviceProperty
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMGetDeviceProperty
---

# NdisMGetDeviceProperty function


## -description

The
  <b>NdisMGetDeviceProperty</b> function retrieves device objects required to set up communication with a
  miniport driver through a bus driver.

## -parameters

### -param MiniportAdapterHandle 

[in]
The NDIS handle that identifies the miniport adapter. This handle was originally passed to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.

### -param PhysicalDeviceObject 

[out, optional]
A pointer to a caller-allocated buffer. The buffer receives a pointer to a 
     <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure that represents the
     physical device for the miniport adapter. This pointer is optional.

### -param FunctionalDeviceObject 

[out, optional]
A pointer to a caller-allocated buffer. The buffer receives a pointer to a 
     <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure. 
     <b>DEVICE_OBJECT</b> represents the functional device object that NDIS creates for the physical device.
     This pointer is optional.

### -param NextDeviceObject 

[out, optional]
A pointer to a caller-allocated buffer. The buffer receives a pointer to a 
     <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure that represents the next device object. This next device object is
     preceded in the chain by the functional device object that belongs to the miniport driver. NDIS creates
     this functional device object for the physical device. For example, the next device object could be the
     object that is associated with a bus driver or HAL This pointer is optional.

### -param AllocatedResources 

[out, optional]
A pointer to a caller-allocated buffer that receives a pointer to a 
     CM_RESOURCE_LIST structure. 
     CM_RESOURCE_LIST describes a list of hardware resources that the PnP manager assigns to the
     physical device. This list contains the resources in raw form, that is, not translated by HAL. This
     pointer is optional.

### -param AllocatedResourcesTranslated 

[out, optional]
A pointer to a caller-allocated buffer that receives a pointer to a 
     CM_RESOURCE_LIST structure. 
     CM_RESOURCE_LIST describes a list of hardware resources that the PnP manager assigns to the
     physical device. This list contains the resources in translated form, that is, translated by HAL. This
     pointer is optional.

## -remarks

Miniport drivers must retrieve specific information to set up their communications. Miniport drivers
    for miniport instances that communicate through bus drivers use 
    <b>NdisMGetDeviceProperty</b> to retrieve this information. For example, miniport driver instances that
    attach to Universal Serial Bus (USB) or IEEE 1394 buses require miniport drivers that expose a standard
    NDIS miniport driver interface at their upper edge, and use the class interface for the particular bus at
    their lower edge. To use the USB or 1394 class interface, a miniport driver creates and submits I/O
    Request Packets (IRPs). The miniport driver uses the physical and next-device objects that 
    <b>NdisMGetDeviceProperty</b> retrieves to submit IRPs to the class interface for a particular bus. To
    locate more information about creating and submitting IRPs to bus drivers, see 
    <a href="/windows-hardware/drivers/kernel/handling-irps">Handling IRPs</a>.

Pointers to 
    <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> for the physical, functional, and next device objects that 
    <b>NdisMGetDeviceProperty</b> retrieves are simply handles that are opaque to the miniport driver.

Miniport drivers can call 
    <b>NdisMGetDeviceProperty</b> to retrieve pointers to "raw" or "translated" resources. Raw resources have
    not been translated by HAL; translated resources have been. To locate more information about raw and
    translated resources, see 
    <a href="/previous-versions/windows/hardware/network/ff562374(v=vs.85)">Plug and Play</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>