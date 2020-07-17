---
UID: NE:fwpsk.FWPS_FIELDS_IPSEC_V6_
title: FWPS_FIELDS_IPSEC_V6_ (fwpsk.h)
description: The FWPS_FIELDS_IPSEC_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_IPSEC_V6 run-time filtering layer.
old-location: netvista\fwps_fields_ipsec_v6.htm
tech.root: netvista
ms.assetid: e3141736-6e85-43ad-b7f5-28845a57a75c
ms.date: 05/02/2018
keywords: ["FWPS_FIELDS_IPSEC_V6_ enumeration"]
ms.keywords: FWPS_FIELDS_IPSEC_V6, FWPS_FIELDS_IPSEC_V6 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_IPSEC_V6_, FWPS_FIELD_IPSEC_V6_IP_LOCAL_ADDRESS, FWPS_FIELD_IPSEC_V6_IP_LOCAL_INTERFACE, FWPS_FIELD_IPSEC_V6_IP_LOCAL_PORT, FWPS_FIELD_IPSEC_V6_IP_PROTOCOL, FWPS_FIELD_IPSEC_V6_IP_REMOTE_ADDRESS, FWPS_FIELD_IPSEC_V6_IP_REMOTE_PORT, FWPS_FIELD_IPSEC_V6_MAX, FWPS_FIELD_IPSEC_V6_PROFILE_ID, fwpsk/FWPS_FIELDS_IPSEC_V6, fwpsk/FWPS_FIELD_IPSEC_V6_IP_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_IPSEC_V6_IP_LOCAL_INTERFACE, fwpsk/FWPS_FIELD_IPSEC_V6_IP_LOCAL_PORT, fwpsk/FWPS_FIELD_IPSEC_V6_IP_PROTOCOL, fwpsk/FWPS_FIELD_IPSEC_V6_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_IPSEC_V6_IP_REMOTE_PORT, fwpsk/FWPS_FIELD_IPSEC_V6_MAX, fwpsk/FWPS_FIELD_IPSEC_V6_PROFILE_ID, netvista.fwps_fields_ipsec_v6, wfp_ref_5_const_3_data_fields_33605f4a-08a5-4d7e-bd5c-262711341b18.xml
f1_keywords:
 - "fwpsk/FWPS_FIELDS_IPSEC_V6"
 - "FWPS_FIELDS_IPSEC_V6"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fwpsk.h
api_name:
- FWPS_FIELDS_IPSEC_V6
product:
- Windows
targetos: Windows
req.typenames: FWPS_FIELDS_IPSEC_V6
---

# FWPS_FIELDS_IPSEC_V6_ enumeration


## -description


The FWPS_FIELDS_IPSEC_V6 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_IPSEC_V6 
  <a href="https://docs.microsoft.com/windows/desktop/FWP/management-filtering-layer-identifiers-">run-time filtering layer</a>.


## -enum-fields




### -field FWPS_FIELD_IPSEC_V6_IP_PROTOCOL

The IP protocol number, as specified in RFC 1700.


### -field FWPS_FIELD_IPSEC_V6_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_IPSEC_V6_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_IPSEC_V6_IP_LOCAL_PORT

The local transport protocol port number.


### -field FWPS_FIELD_IPSEC_V6_IP_REMOTE_PORT

The remote transport protocol port number.


### -field FWPS_FIELD_IPSEC_V6_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>) for the network interface associated with the local IP address.


### -field FWPS_FIELD_IPSEC_V6_PROFILE_ID

The profile identifier (network category) of the network interface. The possible network category
     values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_IPSEC_V6_IPSEC_SECURITY_REALM_ID

The IPsec security realm identifier.

<div class="alert"><b>Note</b>  Supported starting with Windows 10.</div>
<div> </div>

### -field FWPS_FIELD_IPSEC_V6_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

