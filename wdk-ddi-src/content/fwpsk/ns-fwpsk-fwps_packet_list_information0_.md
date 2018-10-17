---
UID: NS:fwpsk.FWPS_PACKET_LIST_INFORMATION0_
title: FWPS_PACKET_LIST_INFORMATION0_
author: windows-driver-content
description: The FWPS_PACKET_LIST_INFORMATION0 structure defines information associated with a packet list.Note  FWPS_PACKET_LIST_INFORMATION0 is a specific version of FWPS_PACKET_LIST_INFORMATION.
old-location: netvista\fwps_packet_list_information0.htm
tech.root: netvista
ms.assetid: 1fc6ffb1-c6e9-4bca-9d10-541708fe0086
ms.date: 5/2/2018
ms.keywords: FWPS_PACKET_LIST_INFORMATION0, FWPS_PACKET_LIST_INFORMATION0 structure [Network Drivers Starting with Windows Vista], FWPS_PACKET_LIST_INFORMATION0_, fwpsk/FWPS_PACKET_LIST_INFORMATION0, netvista.fwps_packet_list_information0, wfp_ref_3_struct_3_fwps_P-Z_f2647b5d-3267-4bc2-889e-8fb3a81f6440.xml
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fwpsk.h
api_name:
-	FWPS_PACKET_LIST_INFORMATION0
product:
- Windows
targetos: Windows
req.typenames: FWPS_PACKET_LIST_INFORMATION0
---

# FWPS_PACKET_LIST_INFORMATION0_ structure


## -description


The <b>FWPS_PACKET_LIST_INFORMATION0</b> structure defines information associated with a packet list.
<div class="alert"><b>Note</b>  <b>FWPS_PACKET_LIST_INFORMATION0</b> is a specific version of <b>FWPS_PACKET_LIST_INFORMATION</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -struct-fields




### -field ipsecInformation

An 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552414">FWPS_PACKET_LIST_IPSEC_INFORMATION0</a> structure that contains IPsec information associated with the
     packet list.


### -field fwpInformation

An 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552410">FWPS_PACKET_LIST_FWP_INFORMATION0</a> structure that contains Windows Filtering Platform information
     associated with the packet list.


## -remarks



A callout driver passes a pointer to an FWPS_PACKET_LIST_INFORMATION0 structure to the 
    <a href="https://msdn.microsoft.com/c3391615-963b-4916-9280-ce782269692c">
    FwpsGetPacketListSecurityInformation0</a> function when querying information associated with a packet
    list.




## -see-also




<a href="https://msdn.microsoft.com/e2d3faf3-cd3b-4147-8ceb-5b3f0c257939">
   FWPS_PACKET_LIST_FWP_INFORMATION0</a>



<a href="https://msdn.microsoft.com/bd005dd9-887a-4323-9816-e4a3b96ca53d">
   FWPS_PACKET_LIST_IPSEC_INFORMATION0</a>



<a href="https://msdn.microsoft.com/c3391615-963b-4916-9280-ce782269692c">
   FwpsGetPacketListSecurityInformation0</a>
 

 

