---
UID: NS:fwpsk.FWPS_PACKET_LIST_INFORMATION0_
title: FWPS_PACKET_LIST_INFORMATION0_
author: windows-driver-content
description: The FWPS_PACKET_LIST_INFORMATION0 structure defines information associated with a packet list.Note  FWPS_PACKET_LIST_INFORMATION0 is a specific version of FWPS_PACKET_LIST_INFORMATION.
old-location: netvista\fwps_packet_list_information0.htm
old-project: netvista
ms.assetid: 1fc6ffb1-c6e9-4bca-9d10-541708fe0086
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FWPS_PACKET_LIST_INFORMATION0_, FWPS_PACKET_LIST_INFORMATION0
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
req.alt-api: FWPS_PACKET_LIST_INFORMATION0
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
req.typenames: FWPS_PACKET_LIST_INFORMATION0
---

# FWPS_PACKET_LIST_INFORMATION0_ structure



## -description
The <b>FWPS_PACKET_LIST_INFORMATION0</b> structure defines information associated with a packet list.



## -syntax

````
typedef struct FWPS_PACKET_LIST_INFORMATION0_ {
  FWPS_PACKET_LIST_IPSEC_INFORMATION0 ipsecInformation;
  FWPS_PACKET_LIST_FWP_INFORMATION0   fwpInformation;
} FWPS_PACKET_LIST_INFORMATION0;
````


## -struct-fields

### -field ipsecInformation

An 
     <a href="..\fwpsk\ns-fwpsk-fwps_packet_list_ipsec_information0_.md">FWPS_PACKET_LIST_IPSEC_INFORMATION0</a> structure that contains IPsec information associated with the
     packet list.


### -field fwpInformation

An 
     <a href="..\fwpsk\ns-fwpsk-fwps_packet_list_fwp_information0_.md">FWPS_PACKET_LIST_FWP_INFORMATION0</a> structure that contains Windows Filtering Platform information
     associated with the packet list.


## -remarks
A callout driver passes a pointer to an FWPS_PACKET_LIST_INFORMATION0 structure to the 
    <a href="..\fwpsk\nf-fwpsk-fwpsgetpacketlistsecurityinformation0.md">
    FwpsGetPacketListSecurityInformation0</a> function when querying information associated with a packet
    list.


## -see-also
<dl>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsgetpacketlistsecurityinformation0.md">
   FwpsGetPacketListSecurityInformation0</a>
</dt>
<dt>
<a href="..\fwpsk\ns-fwpsk-fwps_packet_list_fwp_information0_.md">
   FWPS_PACKET_LIST_FWP_INFORMATION0</a>
</dt>
<dt>
<a href="..\fwpsk\ns-fwpsk-fwps_packet_list_ipsec_information0_.md">
   FWPS_PACKET_LIST_IPSEC_INFORMATION0</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_PACKET_LIST_INFORMATION0 structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

