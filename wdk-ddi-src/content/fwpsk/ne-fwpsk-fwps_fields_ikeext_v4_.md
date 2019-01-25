---
UID: NE:fwpsk.FWPS_FIELDS_IKEEXT_V4_
title: FWPS_FIELDS_IKEEXT_V4_ (fwpsk.h)
description: The FWPS_FIELDS_IKEEXT_V4 enumeration type specifies the data field identifiers for the FWPS_LAYER_IKEEXT_V4 run-time filtering layer.
old-location: netvista\fwps_fields_ikeext_v4.htm
tech.root: netvista
ms.assetid: 5d2a7eda-343b-4713-9481-6f54f713811f
ms.date: 05/02/2018
ms.keywords: FWPS_FIELDS_IKEEXT_V4, FWPS_FIELDS_IKEEXT_V4 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_IKEEXT_V4_, FWPS_FIELD_IKEEXT_V4_IP_LOCAL_ADDRESS, FWPS_FIELD_IKEEXT_V4_IP_LOCAL_INTERFACE, FWPS_FIELD_IKEEXT_V4_IP_REMOTE_ADDRESS, FWPS_FIELD_IKEEXT_V4_MAX, FWPS_FIELD_IKEEXT_V4_PROFILE_ID, fwpsk/FWPS_FIELDS_IKEEXT_V4, fwpsk/FWPS_FIELD_IKEEXT_V4_IP_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_IKEEXT_V4_IP_LOCAL_INTERFACE, fwpsk/FWPS_FIELD_IKEEXT_V4_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_IKEEXT_V4_MAX, fwpsk/FWPS_FIELD_IKEEXT_V4_PROFILE_ID, netvista.fwps_fields_ikeext_v4, wfp_ref_5_const_3_data_fields_c891b6cd-82a0-45f1-9284-97d89aaeef6e.xml
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
-	FWPS_FIELDS_IKEEXT_V4
product:
- Windows
targetos: Windows
req.typenames: FWPS_FIELDS_IKEEXT_V4
---

# FWPS_FIELDS_IKEEXT_V4_ enumeration


## -description


The FWPS_FIELDS_IKEEXT_V4 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_IKEEXT_V4 
  <a href="https://msdn.microsoft.com/library/windows/desktop/aa366492">run-time filtering layer</a>.


## -enum-fields




### -field FWPS_FIELD_IKEEXT_V4_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_IKEEXT_V4_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_IKEEXT_V4_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>) for the network interface associated with the local IP address.


### -field FWPS_FIELD_IKEEXT_V4_PROFILE_ID

The profile identifier (network category) of the network interface. The possible network category
     values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_IKEEXT_V4_IPSEC_SECURITY_REALM_ID

The IPsec security realm identifier.

<div class="alert"><b>Note</b>  Supported starting with Windows 10.</div>
<div> </div>

### -field FWPS_FIELD_IKEEXT_V4_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>
 

 

