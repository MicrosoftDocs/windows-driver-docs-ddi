---
UID: NE:fwpsk.FWPS_FIELDS_IKEEXT_V6_
title: FWPS_FIELDS_IKEEXT_V6_
author: windows-driver-content
description: The FWPS_FIELDS_IKEEXT_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_IKEEXT_V6 run-time filtering layer.
old-location: netvista\fwps_fields_ikeext_v6.htm
old-project: netvista
ms.assetid: 1e355322-23ae-4cc6-af2f-5852515c8056
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FWPS_FIELDS_IKEEXT_V6_, FWPS_FIELDS_IKEEXT_V6
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
req.alt-api: FWPS_FIELDS_IKEEXT_V6
req.alt-loc: fwpsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: FWPS_FIELDS_IKEEXT_V6
---

# FWPS_FIELDS_IKEEXT_V6_ enumeration



## -description
The FWPS_FIELDS_IKEEXT_V6 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_IKEEXT_V6 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layer</a>.



## -syntax

````
typedef enum FWPS_FIELDS_IKEEXT_V6_ { 
  FWPS_FIELD_IKEEXT_V6_IP_LOCAL_ADDRESS,
  FWPS_FIELD_IKEEXT_V6_IP_REMOTE_ADDRESS,
  FWPS_FIELD_IKEEXT_V6_IP_LOCAL_INTERFACE,
#if (NTDDI_VERSION >= NTDDI_WIN7)
  FWPS_FIELD_IKEEXT_V6_PROFILE_ID,
#endif 
  FWPS_FIELD_IKEEXT_V6_MAX
} FWPS_FIELDS_IKEEXT_V6;
````


## -enum-fields

### -field FWPS_FIELD_IKEEXT_V6_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_IKEEXT_V6_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_IKEEXT_V6_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>) for the network interface associated with the
     local IP address.


### -field FWPS_FIELD_IKEEXT_V6_PROFILE_ID

The profile identifier (network category) of the network interface. The possible network category
     values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_IKEEXT_V6_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks
