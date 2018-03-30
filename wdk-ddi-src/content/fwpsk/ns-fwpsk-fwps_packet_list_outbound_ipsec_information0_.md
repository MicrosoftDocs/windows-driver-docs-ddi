---
UID: NS:fwpsk.FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0_
title: FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0_
author: windows-driver-content
description: The FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0 structure defines IPsec information associated with outbound packet data.Note  FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0 is a specific version of FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION.
old-location: netvista\fwps_packet_list_outbound_ipsec_information0.htm
old-project: netvista
ms.assetid: 18312157-f41c-474d-9cf4-446d8b189c4d
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0, FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0 structure [Network Drivers Starting with Windows Vista], FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0_, fwpsk/FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0, netvista.fwps_packet_list_outbound_ipsec_information0, wfp_ref_3_struct_3_fwps_P-Z_b5959556-81fe-4c93-9700-2214fee005c5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
-	FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0
product: Windows
targetos: Windows
req.typenames: FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0
---

# FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0_ structure


## -description


The <b>FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0</b> structure defines IPsec information associated with
  outbound packet data.
<div class="alert"><b>Note</b>  <b>FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0</b> is a specific version of <b>FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -struct-fields




### -field isIPsecPolicyMatch

A value that indicates whether the packet list matched an IPsec filter at the outbound transport
     layer.


### -field isTransportPolicyMatch

A value that indicates whether the packet list matched an IPsec transport mode filter at the outbound
     transport layer.


### -field isTunnelPolicyMatch

A value that indicates whether the packet list matched an IPsec tunnel mode filter at the outbound
     transport layer.


### -field isTunnelIPinIP

A value that indicates whether the packet list matched an IP-in-IP filter for IPsec tunnel mode.


## -remarks



An FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0 structure is included as a member of the 
    <a href="https://msdn.microsoft.com/bd005dd9-887a-4323-9816-e4a3b96ca53d">
    FWPS_PACKET_LIST_IPSEC_INFORMATION0</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/bd005dd9-887a-4323-9816-e4a3b96ca53d">
   FWPS_PACKET_LIST_IPSEC_INFORMATION0</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0 structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
