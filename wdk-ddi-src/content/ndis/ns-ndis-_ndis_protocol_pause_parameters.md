---
UID: NS:ndis._NDIS_PROTOCOL_PAUSE_PARAMETERS
title: "_NDIS_PROTOCOL_PAUSE_PARAMETERS"
author: windows-driver-content
description: NDIS passes an NDIS_PROTOCOL_PAUSE_PARAMETERS structure to a protocol driver when it calls the ProtocolNetPnPEvent function to indicate a NetEventPause event.
old-location: netvista\ndis_protocol_pause_parameters.htm
old-project: netvista
ms.assetid: 7754d47f-9e21-44c7-8a6f-141d18623ddf
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PNDIS_PROTOCOL_PAUSE_PARAMETERS, NDIS_PROTOCOL_PAUSE_PARAMETERS, NDIS_PROTOCOL_PAUSE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_PROTOCOL_PAUSE_PARAMETERS, PNDIS_PROTOCOL_PAUSE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PROTOCOL_PAUSE_PARAMETERS, ndis/NDIS_PROTOCOL_PAUSE_PARAMETERS, ndis/PNDIS_PROTOCOL_PAUSE_PARAMETERS, netvista.ndis_protocol_pause_parameters, protocol_structures_ref_0b5004b2-d77f-427a-8473-f0ffb13a09f4.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_PROTOCOL_PAUSE_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_PROTOCOL_PAUSE_PARAMETERS, *PNDIS_PROTOCOL_PAUSE_PARAMETERS
---

# _NDIS_PROTOCOL_PAUSE_PARAMETERS structure


## -description


NDIS passes an NDIS_PROTOCOL_PAUSE_PARAMETERS structure to a protocol driver when it calls the 
  <a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a> function to
  indicate a 
  <b>NetEventPause</b> event.


## -syntax


````
typedef struct _NDIS_PROTOCOL_PAUSE_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  ULONG              PauseReason;
} NDIS_PROTOCOL_PAUSE_PARAMETERS, *PNDIS_PROTOCOL_PAUSE_PARAMETERS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_PROTOCOL_PAUSE_PARAMETERS structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_PROTOCOL_PAUSE_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_PROTOCOL_PAUSE_PARAMETERS_REVISION_1.


### -field Flags

Reserved.


### -field PauseReason

<div class="alert"><b>Note</b>  This member is deprecated for NDIS 6.40 and later drivers.</div>
<div> </div>
The value will always be NDIS_PAUSE_NDIS_INTERNAL.


## -remarks



To specify the pause parameters for a binding, NDIS passes a pointer to an
    NDIS_PROTOCOL_PAUSE_PARAMETERS structure to the 
    <a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a> function when
    NDIS indicates a 
    <b>NetEventPause</b> event.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PROTOCOL_PAUSE_PARAMETERS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

