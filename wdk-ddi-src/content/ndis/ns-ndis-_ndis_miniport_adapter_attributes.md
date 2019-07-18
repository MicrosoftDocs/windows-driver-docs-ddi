---
UID: NS:ndis._NDIS_MINIPORT_ADAPTER_ATTRIBUTES
title: _NDIS_MINIPORT_ADAPTER_ATTRIBUTES (ndis.h)
description: The NDIS_MINIPORT_ADAPTER_ATTRIBUTES structure is a placeholder for the following structures:\_NDIS_OBJECT_HEADER NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTESNDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
old-location: netvista\ndis_miniport_adapter_attributes.htm
tech.root: netvista
ms.assetid: 41e3c65a-0ab8-4f6f-af49-1aa2edbeda5c
ms.date: 05/02/2018
ms.keywords: NDIS_MINIPORT_ADAPTER_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_ATTRIBUTES union [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_ADAPTER_ATTRIBUTES, PNDIS_MINIPORT_ADAPTER_ATTRIBUTES union pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_ADAPTER_ATTRIBUTES, miniport_structures_ref_dc9acf58-fbc9-4b4c-8c99-33ab7a3bc653.xml, ndis/NDIS_MINIPORT_ADAPTER_ATTRIBUTES, ndis/PNDIS_MINIPORT_ADAPTER_ATTRIBUTES, netvista.ndis_miniport_adapter_attributes
ms.topic: struct
f1_keywords:
 - "ndis/NDIS_MINIPORT_ADAPTER_ATTRIBUTES"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
- ndis.h
api_name:
- NDIS_MINIPORT_ADAPTER_ATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_ADAPTER_ATTRIBUTES, PNDIS_MINIPORT_ADAPTER_ATTRIBUTES
---

# _NDIS_MINIPORT_ADAPTER_ATTRIBUTES structure


## -description


The NDIS_MINIPORT_ADAPTER_ATTRIBUTES structure is a placeholder for the following structures:
  
<dl>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_add_device_registration_attributes">
     NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_registration_attributes">
     NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_general_attributes">
     NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_offload_attributes">
     NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff565926(v=vs.85)">
     NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes">
     NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_ndk_attributes">NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</a>


</dd>
</dl>

## -struct-fields




### -field Header

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.


### -field AddDeviceRegistrationAttributes

An 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_add_device_registration_attributes">
     NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a> structure.


### -field RegistrationAttributes

An 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_registration_attributes">
     NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a> structure.


### -field GeneralAttributes

An 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_general_attributes">
     NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a> structure.


### -field OffloadAttributes

An 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_offload_attributes">
     NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a> structure.


### -field Native_802_11_Attributes

An 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff565926(v=vs.85)">
     NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a> structure.


### -field HardwareAssistAttributes

An 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes">
      NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a> structure.


### -field NDKAttributes

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_ndk_attributes">NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</a> structure.


### -field PacketDirectAttributes

 




## -remarks



Miniport drivers pass these structures to the 
    <i>MiniportAttributes</i> parameter of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_general_attributes">
   NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes">
   NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff565926(v=vs.85)">
   NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_ndk_attributes">NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_offload_attributes">
   NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_registration_attributes">
   NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_add_device_registration_attributes">
   NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
 

 

