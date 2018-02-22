---
UID: NE:fwpsk.FWPS_FIELDS_ALE_FLOW_ESTABLISHED_V4_
title: FWPS_FIELDS_ALE_FLOW_ESTABLISHED_V4_
author: windows-driver-content
description: The FWPS_FIELDS_ALE_FLOW_ESTABLISHED_V4 enumeration type specifies the data field identifiers for the FWPS_LAYER_ALE_FLOW_ESTABLISHED_V4 and FWPS_LAYER_ALE_FLOW_ESTABLISHED_V4_DISCARD run-time filtering layers.
old-location: netvista\fwps_fields_ale_flow_established_v4.htm
old-project: netvista
ms.assetid: 643de915-f0d6-4d3d-a0b9-a86e6beba8fd
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_INTERFACE_TYPE, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_DIRECTION, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_ADDRESS_TYPE, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_REMOTE_ADDRESS, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_REMOTE_USER_ID, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_REMOTE_USER_ID, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_DESTINATION_ADDRESS_TYPE, wfp_ref_5_const_3_data_fields_eae24291-c25f-4f7e-aded-8cd2cef69ef5.xml, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_DIRECTION, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_MAX, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_REMOTE_MACHINE_ID, FWPS_FIELDS_ALE_FLOW_ESTABLISHED_V4, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_INTERFACE_TYPE, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_PROTOCOL, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_PORT, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_REMOTE_PORT, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_APP_ID, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_MAX, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_REMOTE_PORT, FWPS_FIELDS_ALE_FLOW_ESTABLISHED_V4_, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_PROTOCOL, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_ADDRESS, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_ORIGINAL_APP_ID, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_REMOTE_MACHINE_ID, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_FLAGS, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_TUNNEL_TYPE, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_ORIGINAL_APP_ID, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_PORT, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_REMOTE_ADDRESS, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_FLAGS, FWPS_FIELDS_ALE_FLOW_ESTABLISHED_V4 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_PACKAGE_ID, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_USER_ID, netvista.fwps_fields_ale_flow_established_v4, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_INTERFACE, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_DESTINATION_ADDRESS_TYPE, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_INTERFACE, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_PACKAGE_ID, fwpsk/FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_APP_ID, fwpsk/FWPS_FIELDS_ALE_FLOW_ESTABLISHED_V4, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_USER_ID, FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_TUNNEL_TYPE
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fwpsk.h
apiname:
-	FWPS_FIELDS_ALE_FLOW_ESTABLISHED_V4
product: Windows
targetos: Windows
req.typenames: FWPS_FIELDS_ALE_FLOW_ESTABLISHED_V4
---

# FWPS_FIELDS_ALE_FLOW_ESTABLISHED_V4_ enumeration


## -description


The FWPS_FIELDS_ALE_FLOW_ESTABLISHED_V4 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_ALE_FLOW_ESTABLISHED_V4 and FWPS_LAYER_ALE_FLOW_ESTABLISHED_V4_DISCARD 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layers</a>.


## -syntax


````
typedef enum FWPS_FIELDS_ALE_FLOW_ESTABLISHED_V4_ { 
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_APP_ID,
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_USER_ID,
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_ADDRESS,
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_ADDRESS_TYPE,
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_PORT,
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_PROTOCOL,
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_REMOTE_ADDRESS,
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_REMOTE_PORT,
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_REMOTE_USER_ID,
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_REMOTE_MACHINE_ID,
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_DESTINATION_ADDRESS_TYPE,
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_INTERFACE,
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_DIRECTION,
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_INTERFACE_TYPE,
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_TUNNEL_TYPE,
#if (NTDDI_VERSION >= NTDDI_WIN6SP1)
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_FLAGS,
#if (NTDDI_VERSION >= NTDDI_WIN8)
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_ORIGINAL_APP_ID,
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_PACKAGE_ID,
#endif 
#endif 
  FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_MAX
} FWPS_FIELDS_ALE_FLOW_ESTABLISHED_V4;
````


## -enum-fields




### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_APP_ID

The full path of the application.


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_USER_ID

The identifier of the local user.


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_ADDRESS_TYPE

The local IP address type. The possible values are defined by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a> enumeration.


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_PORT

The local transport protocol port number.


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_PROTOCOL

The IP protocol number, as specified in RFC 1700.


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_REMOTE_PORT

The remote transport protocol port number.


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_REMOTE_USER_ID

The identification of the remote user.


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_REMOTE_MACHINE_ID

The identification of the remote machine.


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_DESTINATION_ADDRESS_TYPE

The destination IP address type. The possible values are defined by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a> enumeration.


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>) for the network interface associated with the
     local IP address.


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_DIRECTION



#####  The possible values are:



#### FWP_DIRECTION_INBOUND



#### FWP_DIRECTION_OUTBOUND


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_INTERFACE_TYPE

The type of the local network interface, as defined by the Internet Assigned Numbers Authority
     (IANA). For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_TUNNEL_TYPE

The encapsulation method used by a tunnel if the 
     <b>IfType</b> member of the IP_ADAPTER_ADDRESSES structure is IF_TYPE_TUNNEL. The tunnel type is defined
     by IANA. For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a> and the
     Windows SDK.


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff549942">Filtering Condition Flags</a>.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_ORIGINAL_APP_ID

The full path of the original application for proxy connections. If the application has not been proxied, this path is identical to the xxx_ALE_APP_ID.

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_PACKAGE_ID

The package identifier is a security identifier (SID) that identifies the associated AppContainer process. For more information about the SID structure, see the description for the SID structure in the Microsoft Windows SDK documentation.

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ALE_SECURITY_ATTRIBUTE_FQBN_VALUE


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_COMPARTMENT_ID


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_BITMAP_IP_LOCAL_ADDRESS


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_BITMAP_IP_LOCAL_PORT


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_BITMAP_IP_REMOTE_ADDRESS


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_BITMAP_IP_REMOTE_PORT


### -field FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks



The following macros in 
    <i>Fwpsk.h</i> are defined with FWPS_FIELDS_ALE_FLOW_ESTABLISHED_V4 enumeration
    values:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
#define FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ICMP_TYPE \
        FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_LOCAL_PORT

#define FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_ICMP_CODE \
        FWPS_FIELD_ALE_FLOW_ESTABLISHED_V4_IP_REMOTE_PORT
</pre>
</td>
</tr>
</table></span></div>
These macros are used to access the following IPV4 data fields:






## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a>



<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_FIELDS_ALE_FLOW_ESTABLISHED_V4 enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

