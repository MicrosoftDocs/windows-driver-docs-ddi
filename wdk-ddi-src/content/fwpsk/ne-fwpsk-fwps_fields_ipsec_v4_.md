---
UID: NE:fwpsk.FWPS_FIELDS_IPSEC_V4_
title: FWPS_FIELDS_IPSEC_V4_
author: windows-driver-content
description: The FWPS_FIELDS_IPSEC_V4 enumeration type specifies the data field identifiers for the FWPS_LAYER_IPSEC_V4 run-time filtering layer.
old-location: netvista\fwps_fields_ipsec_v4.htm
old-project: netvista
ms.assetid: 6477bc7f-60b0-4d3c-b8a2-f7d950f60fd2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: FWPS_FIELD_IPSEC_V4_IP_PROTOCOL, fwpsk/FWPS_FIELD_IPSEC_V4_IP_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_IPSEC_V4_IP_REMOTE_PORT, fwpsk/FWPS_FIELD_IPSEC_V4_PROFILE_ID, fwpsk/FWPS_FIELDS_IPSEC_V4, FWPS_FIELD_IPSEC_V4_IP_REMOTE_PORT, fwpsk/FWPS_FIELD_IPSEC_V4_IP_REMOTE_ADDRESS, FWPS_FIELD_IPSEC_V4_IP_LOCAL_INTERFACE, fwpsk/FWPS_FIELD_IPSEC_V4_IP_PROTOCOL, wfp_ref_5_const_3_data_fields_bb6410d7-ae15-417b-be31-80e11bcf612c.xml, FWPS_FIELDS_IPSEC_V4 enumeration [Network Drivers Starting with Windows Vista], fwpsk/FWPS_FIELD_IPSEC_V4_IP_LOCAL_INTERFACE, FWPS_FIELD_IPSEC_V4_IP_LOCAL_ADDRESS, netvista.fwps_fields_ipsec_v4, FWPS_FIELDS_IPSEC_V4, FWPS_FIELDS_IPSEC_V4_, FWPS_FIELD_IPSEC_V4_IP_LOCAL_PORT, fwpsk/FWPS_FIELD_IPSEC_V4_IP_LOCAL_PORT, FWPS_FIELD_IPSEC_V4_PROFILE_ID, fwpsk/FWPS_FIELD_IPSEC_V4_MAX, FWPS_FIELD_IPSEC_V4_MAX, FWPS_FIELD_IPSEC_V4_IP_REMOTE_ADDRESS
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
-	FWPS_FIELDS_IPSEC_V4
product: Windows
targetos: Windows
req.typenames: FWPS_FIELDS_IPSEC_V4
---

# FWPS_FIELDS_IPSEC_V4_ enumeration


## -description


The FWPS_FIELDS_IPSEC_V4 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_IPSEC_V4 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layer</a>.


## -syntax


````
typedef enum FWPS_FIELDS_IPSEC_V4_ { 
  FWPS_FIELD_IPSEC_V4_IP_PROTOCOL,
  FWPS_FIELD_IPSEC_V4_IP_LOCAL_ADDRESS,
  FWPS_FIELD_IPSEC_V4_IP_REMOTE_ADDRESS,
  FWPS_FIELD_IPSEC_V4_IP_LOCAL_PORT,
  FWPS_FIELD_IPSEC_V4_IP_REMOTE_PORT,
  FWPS_FIELD_IPSEC_V4_IP_LOCAL_INTERFACE,
#if (NTDDI_VERSION >= NTDDI_WIN7)
  FWPS_FIELD_IPSEC_V4_PROFILE_ID,
#endif 
  FWPS_FIELD_IPSEC_V4_MAX
} FWPS_FIELDS_IPSEC_V4;
````


## -enum-fields




### -field FWPS_FIELD_IPSEC_V4_IP_PROTOCOL

The IP protocol number, as specified in RFC 1700.


### -field FWPS_FIELD_IPSEC_V4_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_IPSEC_V4_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_IPSEC_V4_IP_LOCAL_PORT

The local transport protocol port number.


### -field FWPS_FIELD_IPSEC_V4_IP_REMOTE_PORT

The remote transport protocol port number.


### -field FWPS_FIELD_IPSEC_V4_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>) for the network interface associated with the
     local IP address.


### -field FWPS_FIELD_IPSEC_V4_PROFILE_ID

The profile identifier (network category) of the network interface. The possible network category
     values are: public (1), private (2), or domain (3).
     
<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div><div> </div>

### -field FWPS_FIELD_IPSEC_V4_IPSEC_SECURITY_REALM_ID



### -field FWPS_FIELD_IPSEC_V4_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

