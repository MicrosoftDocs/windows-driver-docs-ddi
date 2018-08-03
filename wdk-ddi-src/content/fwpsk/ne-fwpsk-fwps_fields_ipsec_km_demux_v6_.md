---
UID: NE:fwpsk.FWPS_FIELDS_IPSEC_KM_DEMUX_V6_
title: FWPS_FIELDS_IPSEC_KM_DEMUX_V6_
author: windows-driver-content
description: The FWPS_FIELDS_IPSEC_KM_DEMUX_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_IPSEC_KM_DEMUX_V6 run-time filtering layer.
old-location: netvista\fwps_fields_ipsec_km_demux_v6.htm
tech.root: netvista
ms.assetid: 343b230c-08ae-4e05-8ab0-03f4c8748a11
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: FWPS_FIELDS_IPSEC_KM_DEMUX_V6, FWPS_FIELDS_IPSEC_KM_DEMUX_V6 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_IPSEC_KM_DEMUX_V6_, FWPS_FIELD_IPSEC_KM_DEMUX_V6_CURRENT_PROFILE_ID, FWPS_FIELD_IPSEC_KM_DEMUX_V6_IP_LOCAL_ADDRESS, FWPS_FIELD_IPSEC_KM_DEMUX_V6_IP_LOCAL_INTERFACE, FWPS_FIELD_IPSEC_KM_DEMUX_V6_IP_REMOTE_ADDRESS, FWPS_FIELD_IPSEC_KM_DEMUX_V6_MAX, FWPS_FIELD_IPSEC_KM_DEMUX_V6_QM_MODE, fwpsk/FWPS_FIELDS_IPSEC_KM_DEMUX_V6, fwpsk/FWPS_FIELD_IPSEC_KM_DEMUX_V6_CURRENT_PROFILE_ID, fwpsk/FWPS_FIELD_IPSEC_KM_DEMUX_V6_IP_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_IPSEC_KM_DEMUX_V6_IP_LOCAL_INTERFACE, fwpsk/FWPS_FIELD_IPSEC_KM_DEMUX_V6_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_IPSEC_KM_DEMUX_V6_MAX, fwpsk/FWPS_FIELD_IPSEC_KM_DEMUX_V6_QM_MODE, netvista.fwps_fields_ipsec_km_demux_v6, wfp_ref_5_const_3_data_fields_3f9c4ab8-b2eb-4663-b4c0-1d0865b94025.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows Vista.
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
-	FWPS_FIELDS_IPSEC_KM_DEMUX_V6
product:
- Windows
targetos: Windows
req.typenames: FWPS_FIELDS_IPSEC_KM_DEMUX_V6
---

# FWPS_FIELDS_IPSEC_KM_DEMUX_V6_ enumeration


## -description


The FWPS_FIELDS_IPSEC_KM_DEMUX_V6 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_IPSEC_KM_DEMUX_V6 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layer</a>.


## -enum-fields




### -field FWPS_FIELD_IPSEC_KM_DEMUX_V6_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_IPSEC_KM_DEMUX_V6_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_IPSEC_KM_DEMUX_V6_QM_MODE

The quick mode (QM) mode.
     

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_FIELD_IPSEC_KM_DEMUX_V6_IP_LOCAL_INTERFACE

The IP local interface.
     

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_FIELD_IPSEC_KM_DEMUX_V6_CURRENT_PROFILE_ID

The profile identifier (network category) of the network interface. The possible network category values are: public (1), private (2), or domain (3). 



<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_FIELD_KM_DEMUX_V6_IPSEC_SECURITY_REALM_ID


### -field FWPS_FIELD_IPSEC_KM_DEMUX_V6_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

