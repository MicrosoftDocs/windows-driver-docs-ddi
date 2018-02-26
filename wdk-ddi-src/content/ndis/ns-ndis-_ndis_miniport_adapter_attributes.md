---
UID: NS:ndis._NDIS_MINIPORT_ADAPTER_ATTRIBUTES
title: "_NDIS_MINIPORT_ADAPTER_ATTRIBUTES"
author: windows-driver-content
description: The NDIS_MINIPORT_ADAPTER_ATTRIBUTES structure is a placeholder for the following structures:\_NDIS_OBJECT_HEADER NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTESNDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
old-location: netvista\ndis_miniport_adapter_attributes.htm
old-project: netvista
ms.assetid: 41e3c65a-0ab8-4f6f-af49-1aa2edbeda5c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , ,, A, B, D, E, I, M, N, NDIS_MINIPORT_ADAPTER_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_ATTRIBUTES union [Network Drivers Starting with Windows Vista], O, P, PNDIS_MINIPORT_ADAPTER_ATTRIBUTES, PNDIS_MINIPORT_ADAPTER_ATTRIBUTES union pointer [Network Drivers Starting with Windows Vista], R, S, T, U, _, _NDIS_MINIPORT_ADAPTER_ATTRIBUTES, miniport_structures_ref_dc9acf58-fbc9-4b4c-8c99-33ab7a3bc653.xml, ndis/NDIS_MINIPORT_ADAPTER_ATTRIBUTES, ndis/PNDIS_MINIPORT_ADAPTER_ATTRIBUTES, netvista.ndis_miniport_adapter_attributes"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NDIS_MINIPORT_ADAPTER_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_ADAPTER_ATTRIBUTES, PNDIS_MINIPORT_ADAPTER_ATTRIBUTES
---

# _NDIS_MINIPORT_ADAPTER_ATTRIBUTES structure


## -description


The NDIS_MINIPORT_ADAPTER_ATTRIBUTES structure is a placeholder for the following structures:
  
<dl>
<dd>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>


</dd>
<dd>

<a href="..\ndis\ns-ndis-_ndis_miniport_add_device_registration_attributes.md">
     NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a>


</dd>
<dd>

<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_registration_attributes.md">
     NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>


</dd>
<dd>

<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_general_attributes.md">
     NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a>


</dd>
<dd>

<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_offload_attributes.md">
     NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>


</dd>
<dd>

<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_native_802_11_attributes.md">
     NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>


</dd>
<dd>

<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes.md">
     NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>


</dd>
<dd>

<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_ndk_attributes.md">NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</a>


</dd>
</dl>

## -syntax


````
typedef union _NDIS_MINIPORT_ADAPTER_ATTRIBUTES {
  NDIS_OBJECT_HEADER                               Header;
  NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES AddDeviceRegistrationAttributes;
  NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES    RegistrationAttributes;
  NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES         GeneralAttributes;
  NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES         OffloadAttributes;
  NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES   Native_802_11_Attributes;
#if  (NDIS_SUPPORT_NDIS61)
  NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES HardwareAssistAttributes;
#endif 
#if (NDIS_SUPPORT_NDIS630)
  NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES             NDKAttributes;
#endif 
} NDIS_MINIPORT_ADAPTER_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_ATTRIBUTES;
````


## -struct-fields




### -field Header

An <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


### -field AddDeviceRegistrationAttributes

An 
     <a href="..\ndis\ns-ndis-_ndis_miniport_add_device_registration_attributes.md">
     NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a> structure.


### -field RegistrationAttributes

An 
     <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_registration_attributes.md">
     NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a> structure.


### -field GeneralAttributes

An 
     <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_general_attributes.md">
     NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a> structure.


### -field OffloadAttributes

An 
     <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_offload_attributes.md">
     NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a> structure.


### -field Native_802_11_Attributes

An 
     <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_native_802_11_attributes.md">
     NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a> structure.


### -field HardwareAssistAttributes

An 
      <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes.md">
      NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a> structure.


### -field NDKAttributes

An <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_ndk_attributes.md">NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</a> structure.


### -field PacketDirectAttributes

 




## -remarks



Miniport drivers pass these structures to the 
    <i>MiniportAttributes</i> parameter of the 
    <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
    NdisMSetMiniportAttributes</a> function.




## -see-also

<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_ndk_attributes.md">NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_native_802_11_attributes.md">
   NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_registration_attributes.md">
   NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_general_attributes.md">
   NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_offload_attributes.md">
   NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_add_device_registration_attributes.md">
   NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a>



<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes.md">
   NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_ADAPTER_ATTRIBUTES union%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

