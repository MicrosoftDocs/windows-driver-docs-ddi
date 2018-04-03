---
UID: NS:ndis._NDIS_MINIPORT_ADAPTER_ATTRIBUTES
title: "_NDIS_MINIPORT_ADAPTER_ATTRIBUTES"
author: windows-driver-content
description: The NDIS_MINIPORT_ADAPTER_ATTRIBUTES structure is a placeholder for the following structures:\_NDIS_OBJECT_HEADER NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTESNDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
old-location: netvista\ndis_miniport_adapter_attributes.htm
old-project: netvista
ms.assetid: 41e3c65a-0ab8-4f6f-af49-1aa2edbeda5c
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDIS_MINIPORT_ADAPTER_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_ATTRIBUTES union [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_ADAPTER_ATTRIBUTES, PNDIS_MINIPORT_ADAPTER_ATTRIBUTES union pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_ADAPTER_ATTRIBUTES, miniport_structures_ref_dc9acf58-fbc9-4b4c-8c99-33ab7a3bc653.xml, ndis/NDIS_MINIPORT_ADAPTER_ATTRIBUTES, ndis/PNDIS_MINIPORT_ADAPTER_ATTRIBUTES, netvista.ndis_miniport_adapter_attributes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_MINIPORT_ADAPTER_ATTRIBUTES
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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/7e8b5dbf-2d56-4278-8953-8e21ba1cee06">
     NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/8f0d539a-50c5-4ecd-b62d-6b32fe7cfaba">
     NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/5423d073-02a5-468b-b91e-713ac67a5253">
     NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/9ce875fc-ed3f-43e9-bfbc-081f02cb1999">
     NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/f841c7f9-9ad3-4b53-b2d9-0d66d6e64b8b">
     NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/b0662a2c-feb6-4d66-89c9-586c2859b78b">
     NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451558">NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</a>


</dd>
</dl>

## -struct-fields




### -field Header

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.


### -field AddDeviceRegistrationAttributes

An 
     <a href="https://msdn.microsoft.com/7e8b5dbf-2d56-4278-8953-8e21ba1cee06">
     NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a> structure.


### -field RegistrationAttributes

An 
     <a href="https://msdn.microsoft.com/8f0d539a-50c5-4ecd-b62d-6b32fe7cfaba">
     NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a> structure.


### -field GeneralAttributes

An 
     <a href="https://msdn.microsoft.com/5423d073-02a5-468b-b91e-713ac67a5253">
     NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a> structure.


### -field OffloadAttributes

An 
     <a href="https://msdn.microsoft.com/9ce875fc-ed3f-43e9-bfbc-081f02cb1999">
     NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a> structure.


### -field Native_802_11_Attributes

An 
     <a href="https://msdn.microsoft.com/f841c7f9-9ad3-4b53-b2d9-0d66d6e64b8b">
     NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a> structure.


### -field HardwareAssistAttributes

An 
      <a href="https://msdn.microsoft.com/b0662a2c-feb6-4d66-89c9-586c2859b78b">
      NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a> structure.


### -field NDKAttributes

An <a href="https://msdn.microsoft.com/library/windows/hardware/hh451558">NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</a> structure.


### -field PacketDirectAttributes

 




## -remarks



Miniport drivers pass these structures to the 
    <i>MiniportAttributes</i> parameter of the 
    <a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
    NdisMSetMiniportAttributes</a> function.




## -see-also




<a href="https://msdn.microsoft.com/5423d073-02a5-468b-b91e-713ac67a5253">
   NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/b0662a2c-feb6-4d66-89c9-586c2859b78b">
   NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/f841c7f9-9ad3-4b53-b2d9-0d66d6e64b8b">
   NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451558">NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/9ce875fc-ed3f-43e9-bfbc-081f02cb1999">
   NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/8f0d539a-50c5-4ecd-b62d-6b32fe7cfaba">
   NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/7e8b5dbf-2d56-4278-8953-8e21ba1cee06">
   NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>
 

 

