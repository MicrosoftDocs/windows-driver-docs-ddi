---
UID: NE:fwpsk.FWPS_FIELDS_OUTBOUND_ICMP_ERROR_V6_
title: FWPS_FIELDS_OUTBOUND_ICMP_ERROR_V6_
author: windows-driver-content
description: The FWPS_FIELDS_OUTBOUND_ICMP_ERROR_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_OUTBOUND_ICMP_ERROR_V6 and FWPS_LAYER_OUTBOUND_ICMP_ERROR_V6_DISCARD run-time filtering layers.
old-location: netvista\fwps_fields_outbound_icmp_error_v6.htm
tech.root: netvista
ms.assetid: 54fb2380-3299-493e-b42b-6561648d4f0a
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: FWPS_FIELDS_OUTBOUND_ICMP_ERROR_V6, FWPS_FIELDS_OUTBOUND_ICMP_ERROR_V6 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_OUTBOUND_ICMP_ERROR_V6_, FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_FLAGS, FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_INTERFACE_INDEX, FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_INTERFACE_QUARANTINE_EPOCH, FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_INTERFACE_TYPE, FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_LOCAL_ADDRESS, FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_LOCAL_ADDRESS_TYPE, FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_LOCAL_INTERFACE, FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_LOCAL_PORT, FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_REMOTE_ADDRESS, FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_REMOTE_PORT, FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_MAX, FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_NEXTHOP_INTERFACE_PROFILE_ID, FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_SUB_INTERFACE_INDEX, FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_TUNNEL_TYPE, fwpsk/FWPS_FIELDS_OUTBOUND_ICMP_ERROR_V6, fwpsk/FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_FLAGS, fwpsk/FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_INTERFACE_INDEX, fwpsk/FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_INTERFACE_QUARANTINE_EPOCH, fwpsk/FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_INTERFACE_TYPE, fwpsk/FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_LOCAL_INTERFACE, fwpsk/FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_LOCAL_PORT, fwpsk/FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_REMOTE_PORT, fwpsk/FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_MAX, fwpsk/FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_NEXTHOP_INTERFACE_PROFILE_ID, fwpsk/FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_SUB_INTERFACE_INDEX, fwpsk/FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_TUNNEL_TYPE, netvista.fwps_fields_outbound_icmp_error_v6, wfp_ref_5_const_3_data_fields_6b020d8c-912d-4684-8096-2bb815e26134.xml
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
-	FWPS_FIELDS_OUTBOUND_ICMP_ERROR_V6
product:
- Windows
targetos: Windows
req.typenames: FWPS_FIELDS_OUTBOUND_ICMP_ERROR_V6
---

# FWPS_FIELDS_OUTBOUND_ICMP_ERROR_V6_ enumeration


## -description


The FWPS_FIELDS_OUTBOUND_ICMP_ERROR_V6 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_OUTBOUND_ICMP_ERROR_V6 and FWPS_LAYER_OUTBOUND_ICMP_ERROR_V6_DISCARD 
  <a href="https://msdn.microsoft.com/library/windows/desktop/aa366492">run-time filtering layers</a>.


## -enum-fields




### -field FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_LOCAL_ADDRESS_TYPE

The local IP address type. The possible values are defined by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a> enumeration.


### -field FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>) for the network interface associated with the
     local IP address.


### -field FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_LOCAL_PORT

The local transport protocol port number.


### -field FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_REMOTE_PORT

The remote transport protocol port number.


### -field FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_INTERFACE_INDEX

The index of the network interface, as enumerated by the network stack.


### -field FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_SUB_INTERFACE_INDEX

The index of the logical network interface, as enumerated by the network stack.


### -field FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_INTERFACE_TYPE

The type of the network interface, as defined by the Internet Assigned Numbers Authority (IANA).
     For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.


### -field FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_TUNNEL_TYPE

The encapsulation method used by a tunnel if the 
     <b>IfType</b> member of the IP_ADAPTER_ADDRESSES structure is IF_TYPE_TUNNEL. The tunnel type is defined
     by IANA. For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a> and the
     Windows SDK.


### -field FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff549942">Filtering Condition Flags</a>.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_NEXTHOP_INTERFACE_PROFILE_ID

The profile identifier (network category) of the next-hop interface. The possible network category
     values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_INTERFACE_QUARANTINE_EPOCH

The time that has passed since the last media state change occurred for the network interface.
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_COMPARTMENT_ID

The compartment that the network interface belongs to.

<div class="alert"><b>Note</b>  Supported starting with Windows 10, version 1703.</div>
<div> </div>

### -field FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks



The following macros are defined by using enumeration values of the FWPS_FIELDS_OUTBOUND_ICMP_ERROR_V6
    enumeration type:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
#define FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_ICMP_TYPE \
        FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_LOCAL_PORT

#define FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_ICMP_CODE \
        FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_IP_REMOTE_PORT
</pre>
</td>
</tr>
</table></span></div>
These macros are used to access the following IPV6 data fields:

FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_ICMP_TYPE  
The ICMP type field, as specified in RFC 792.

FWPS_FIELD_OUTBOUND_ICMP_ERROR_V6_ICMP_CODE  
The ICMP code field, as specified in RFC 792.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a>
 

 

