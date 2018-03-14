---
UID: NE:fwpsk.FWPS_FIELDS_STREAM_V4_
title: FWPS_FIELDS_STREAM_V4_
author: windows-driver-content
description: The FWPS_FIELDS_STREAM_V4 enumeration type specifies the data field identifiers for the FWPS_LAYER_STREAM_V4 and FWPS_LAYER_STREAM_V4_DISCARD run-time filtering layers.
old-location: netvista\fwps_fields_stream_v4.htm
old-project: netvista
ms.assetid: 1225f28d-3b89-4b14-82c3-5162de9fe8fd
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FWPS_FIELDS_STREAM_V4, FWPS_FIELDS_STREAM_V4 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_STREAM_V4_, FWPS_FIELD_STREAM_V4_DIRECTION, FWPS_FIELD_STREAM_V4_FLAGS, FWPS_FIELD_STREAM_V4_IP_LOCAL_ADDRESS, FWPS_FIELD_STREAM_V4_IP_LOCAL_ADDRESS_TYPE, FWPS_FIELD_STREAM_V4_IP_LOCAL_PORT, FWPS_FIELD_STREAM_V4_IP_REMOTE_ADDRESS, FWPS_FIELD_STREAM_V4_IP_REMOTE_PORT, FWPS_FIELD_STREAM_V4_MAX, fwpsk/FWPS_FIELDS_STREAM_V4, fwpsk/FWPS_FIELD_STREAM_V4_DIRECTION, fwpsk/FWPS_FIELD_STREAM_V4_FLAGS, fwpsk/FWPS_FIELD_STREAM_V4_IP_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_STREAM_V4_IP_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_STREAM_V4_IP_LOCAL_PORT, fwpsk/FWPS_FIELD_STREAM_V4_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_STREAM_V4_IP_REMOTE_PORT, fwpsk/FWPS_FIELD_STREAM_V4_MAX, netvista.fwps_fields_stream_v4, wfp_ref_5_const_3_data_fields_767d81c5-f927-4512-812d-396966457b7a.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fwpsk.h
api_name:
-	FWPS_FIELDS_STREAM_V4
product: Windows
targetos: Windows
req.typenames: FWPS_FIELDS_STREAM_V4
---

# FWPS_FIELDS_STREAM_V4_ enumeration


## -description


The FWPS_FIELDS_STREAM_V4 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_STREAM_V4 and FWPS_LAYER_STREAM_V4_DISCARD 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layers</a>.


## -syntax


````
typedef enum FWPS_FIELDS_STREAM_V4_ { 
  FWPS_FIELD_STREAM_V4_IP_LOCAL_ADDRESS,
  FWPS_FIELD_STREAM_V4_IP_LOCAL_ADDRESS_TYPE,
  FWPS_FIELD_STREAM_V4_IP_REMOTE_ADDRESS,
  FWPS_FIELD_STREAM_V4_IP_LOCAL_PORT,
  FWPS_FIELD_STREAM_V4_IP_REMOTE_PORT,
  FWPS_FIELD_STREAM_V4_DIRECTION,
#if (NTDDI_VERSION >= NTDDI_WIN6SP1
  FWPS_FIELD_STREAM_V4_FLAGS,
#endif 
  FWPS_FIELD_STREAM_V4_MAX
} FWPS_FIELDS_STREAM_V4;
````


## -enum-fields




### -field FWPS_FIELD_STREAM_V4_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_STREAM_V4_IP_LOCAL_ADDRESS_TYPE

The local IP address type. The possible values are defined by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a> enumeration.


### -field FWPS_FIELD_STREAM_V4_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_STREAM_V4_IP_LOCAL_PORT

The local transport protocol port number.


### -field FWPS_FIELD_STREAM_V4_IP_REMOTE_PORT

The remote transport protocol port number.


### -field FWPS_FIELD_STREAM_V4_DIRECTION



#####  The possible values are:



#### FWP_DIRECTION_INBOUND



#### FWP_DIRECTION_OUTBOUND


### -field FWPS_FIELD_STREAM_V4_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff549942">Filtering Condition Flags</a>.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field FWPS_FIELD_STREAM_V4_COMPARTMENT_ID


### -field FWPS_FIELD_STREAM_V4_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_FIELDS_STREAM_V4 enumeration%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

