---
UID: NE:fwpsk.FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6_
title: FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6_
author: windows-driver-content
description: The FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_NAME_RESOLUTION_CACHE_V6 run-time filtering layer.
old-location: netvista\fwps_fields_name_resolution_cache_v6.htm
old-project: netvista
ms.assetid: 78d2ec8f-fbee-4bad-bc84-b10495c24399
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6, FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6_, FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_ALE_APP_ID, FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_ALE_USER_ID, FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_IP_REMOTE_ADDRESS, FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_MAX, FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_PEER_NAME, fwpsk/FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6, fwpsk/FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_ALE_APP_ID, fwpsk/FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_ALE_USER_ID, fwpsk/FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_MAX, fwpsk/FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_PEER_NAME, netvista.fwps_fields_name_resolution_cache_v6, wfp_ref_5_const_3_data_fields_53aef03d-34ba-4bfa-81fd-5329f78dcab7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 7.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fwpsk.h
api_name:
-	FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6
product: Windows
targetos: Windows
req.typenames: FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6
---

# FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6_ enumeration


## -description


The FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6 enumeration type specifies the data field identifiers for
  the FWPS_LAYER_NAME_RESOLUTION_CACHE_V6 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layer</a>.


## -syntax


````
typedef enum FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6_ { 
  FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_ALE_USER_ID,
  FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_ALE_APP_ID,
  FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_IP_REMOTE_ADDRESS,
  FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_PEER_NAME,
  FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_MAX
} FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6;
````


## -enum-fields




### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_ALE_USER_ID

The identifier of the local user.


### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_ALE_APP_ID

The full path of the application.


### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_PEER_NAME

The machine name that is associated with the destination IP address.


### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_COMPARTMENT_ID


### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

