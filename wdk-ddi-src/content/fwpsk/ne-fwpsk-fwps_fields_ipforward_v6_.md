---
UID: NE:fwpsk.FWPS_FIELDS_IPFORWARD_V6_
title: FWPS_FIELDS_IPFORWARD_V6_
author: windows-driver-content
description: The FWPS_FIELDS_IPFORWARD_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_IPFORWARD_V6 and FWPS_LAYER_IPFORWARD_V6_DISCARD run-time filtering layers.
old-location: netvista\fwps_fields_ipforward_v6.htm
old-project: netvista
ms.assetid: 6c3d1da8-0498-4d0f-a4d1-89763a8420f6
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: FWPS_FIELDS_IPFORWARD_V6, FWPS_FIELDS_IPFORWARD_V6 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_IPFORWARD_V6_, FWPS_FIELD_IPFORWARD_V6_ARRIVAL_INTERFACE_PROFILE_ID, FWPS_FIELD_IPFORWARD_V6_DESTINATION_INTERFACE_INDEX, FWPS_FIELD_IPFORWARD_V6_DESTINATION_SUB_INTERFACE_INDEX, FWPS_FIELD_IPFORWARD_V6_FLAGS, FWPS_FIELD_IPFORWARD_V6_IP_DESTINATION_ADDRESS, FWPS_FIELD_IPFORWARD_V6_IP_DESTINATION_ADDRESS_TYPE, FWPS_FIELD_IPFORWARD_V6_IP_FORWARD_INTERFACE, FWPS_FIELD_IPFORWARD_V6_IP_LOCAL_INTERFACE, FWPS_FIELD_IPFORWARD_V6_IP_PHYSICAL_ARRIVAL_INTERFACE, FWPS_FIELD_IPFORWARD_V6_IP_PHYSICAL_NEXTHOP_INTERFACE, FWPS_FIELD_IPFORWARD_V6_IP_SOURCE_ADDRESS, FWPS_FIELD_IPFORWARD_V6_MAX, FWPS_FIELD_IPFORWARD_V6_NEXTHOP_INTERFACE_PROFILE_ID, FWPS_FIELD_IPFORWARD_V6_SOURCE_INTERFACE_INDEX, FWPS_FIELD_IPFORWARD_V6_SOURCE_SUB_INTERFACE_INDEX, fwpsk/FWPS_FIELDS_IPFORWARD_V6, fwpsk/FWPS_FIELD_IPFORWARD_V6_ARRIVAL_INTERFACE_PROFILE_ID, fwpsk/FWPS_FIELD_IPFORWARD_V6_DESTINATION_INTERFACE_INDEX, fwpsk/FWPS_FIELD_IPFORWARD_V6_DESTINATION_SUB_INTERFACE_INDEX, fwpsk/FWPS_FIELD_IPFORWARD_V6_FLAGS, fwpsk/FWPS_FIELD_IPFORWARD_V6_IP_DESTINATION_ADDRESS, fwpsk/FWPS_FIELD_IPFORWARD_V6_IP_DESTINATION_ADDRESS_TYPE, fwpsk/FWPS_FIELD_IPFORWARD_V6_IP_FORWARD_INTERFACE, fwpsk/FWPS_FIELD_IPFORWARD_V6_IP_LOCAL_INTERFACE, fwpsk/FWPS_FIELD_IPFORWARD_V6_IP_PHYSICAL_ARRIVAL_INTERFACE, fwpsk/FWPS_FIELD_IPFORWARD_V6_IP_PHYSICAL_NEXTHOP_INTERFACE, fwpsk/FWPS_FIELD_IPFORWARD_V6_IP_SOURCE_ADDRESS, fwpsk/FWPS_FIELD_IPFORWARD_V6_MAX, fwpsk/FWPS_FIELD_IPFORWARD_V6_NEXTHOP_INTERFACE_PROFILE_ID, fwpsk/FWPS_FIELD_IPFORWARD_V6_SOURCE_INTERFACE_INDEX, fwpsk/FWPS_FIELD_IPFORWARD_V6_SOURCE_SUB_INTERFACE_INDEX, netvista.fwps_fields_ipforward_v6, wfp_ref_5_const_3_data_fields_026b178c-e371-48aa-969c-defb3d26aea3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Unless otherwise noted, supported starting with Windows Vista.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fwpsk.h
api_name:
-	FWPS_FIELDS_IPFORWARD_V6
product:
- Windows
targetos: Windows
req.typenames: FWPS_FIELDS_IPFORWARD_V6
---

# FWPS_FIELDS_IPFORWARD_V6_ enumeration


## -description


The FWPS_FIELDS_IPFORWARD_V6 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_IPFORWARD_V6 and FWPS_LAYER_IPFORWARD_V6_DISCARD 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layers</a>.


## -enum-fields




### -field FWPS_FIELD_IPFORWARD_V6_IP_SOURCE_ADDRESS

The source IP address.


### -field FWPS_FIELD_IPFORWARD_V6_IP_DESTINATION_ADDRESS

The destination IP address.


### -field FWPS_FIELD_IPFORWARD_V6_IP_DESTINATION_ADDRESS_TYPE

The destination IP address type. The possible values are defined by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a> enumeration.


### -field FWPS_FIELD_IPFORWARD_V6_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>) for the network interface associated with the
     local IP address.


### -field FWPS_FIELD_IPFORWARD_V6_IP_FORWARD_INTERFACE

The LUID for the network interface on which the packet being forwarded is to be sent out.


### -field FWPS_FIELD_IPFORWARD_V6_SOURCE_INTERFACE_INDEX

The index of the source network interface, as enumerated by the network stack.


### -field FWPS_FIELD_IPFORWARD_V6_SOURCE_SUB_INTERFACE_INDEX

The index of the source logical network interface, as enumerated by the network stack.


### -field FWPS_FIELD_IPFORWARD_V6_DESTINATION_INTERFACE_INDEX

The index of the destination network interface, as enumerated by the network stack.


### -field FWPS_FIELD_IPFORWARD_V6_DESTINATION_SUB_INTERFACE_INDEX

The index of the destination logical network interface, as enumerated by the network stack.


### -field FWPS_FIELD_IPFORWARD_V6_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff549942">Filtering Condition Flags</a>.


### -field FWPS_FIELD_IPFORWARD_V6_IP_PHYSICAL_ARRIVAL_INTERFACE

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a> for the physical network interface that the
     packet first arrived on.
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_IPFORWARD_V6_ARRIVAL_INTERFACE_PROFILE_ID

The profile identifier (network category) of the arrival interface. The possible network category
     values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_IPFORWARD_V6_IP_PHYSICAL_NEXTHOP_INTERFACE

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a> for the physical network interface that will be
     used to continue forwarding of the outbound packet.
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_IPFORWARD_V6_NEXTHOP_INTERFACE_PROFILE_ID

The profile identifier (network category) of the next-hop interface. The possible network category
     values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_IPFORWARD_V6_COMPARTMENT_ID


### -field FWPS_FIELD_IPFORWARD_V6_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a>
 

 

