---
UID: NS:fwpsk.FWPS_PACKET_LIST_INFORMATION0_
title: FWPS_PACKET_LIST_INFORMATION0_
author: windows-driver-content
description: The FWPS_PACKET_LIST_INFORMATION0 structure defines information associated with a packet list.Note  FWPS_PACKET_LIST_INFORMATION0 is a specific version of FWPS_PACKET_LIST_INFORMATION.
old-location: netvista\fwps_packet_list_information0.htm
old-project: netvista
ms.assetid: 1fc6ffb1-c6e9-4bca-9d10-541708fe0086
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FWPS_PACKET_LIST_INFORMATION0, FWPS_PACKET_LIST_INFORMATION0 structure [Network Drivers Starting with Windows Vista], FWPS_PACKET_LIST_INFORMATION0_, fwpsk/FWPS_PACKET_LIST_INFORMATION0, netvista.fwps_packet_list_information0, wfp_ref_3_struct_3_fwps_P-Z_f2647b5d-3267-4bc2-889e-8fb3a81f6440.xml
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
-	FWPS_PACKET_LIST_INFORMATION0
product: Windows
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
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_PACKET_LIST_INFORMATION0 structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
