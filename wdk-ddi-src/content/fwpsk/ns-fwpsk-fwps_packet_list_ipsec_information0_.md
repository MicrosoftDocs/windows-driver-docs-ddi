---
UID: NS:fwpsk.FWPS_PACKET_LIST_IPSEC_INFORMATION0_
title: FWPS_PACKET_LIST_IPSEC_INFORMATION0_ (fwpsk.h)
description: The FWPS_PACKET_LIST_IPSEC_INFORMATION0 structure defines IPsec information associated with a packet list.Note  FWPS_PACKET_LIST_IPSEC_INFORMATION0 is a specific version of FWPS_PACKET_LIST_IPSEC_INFORMATION.
old-location: netvista\fwps_packet_list_ipsec_information0.htm
tech.root: netvista
ms.assetid: bd005dd9-887a-4323-9816-e4a3b96ca53d
ms.date: 05/02/2018
keywords: ["FWPS_PACKET_LIST_IPSEC_INFORMATION0_ structure"]
ms.keywords: FWPS_PACKET_LIST_IPSEC_INFORMATION0, FWPS_PACKET_LIST_IPSEC_INFORMATION0 structure [Network Drivers Starting with Windows Vista], FWPS_PACKET_LIST_IPSEC_INFORMATION0_, fwpsk/FWPS_PACKET_LIST_IPSEC_INFORMATION0, netvista.fwps_packet_list_ipsec_information0, wfp_ref_3_struct_3_fwps_P-Z_066086e3-4389-4449-b47a-ad9661eef344.xml
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
targetos: Windows
req.typenames: FWPS_PACKET_LIST_IPSEC_INFORMATION0
f1_keywords:
 - FWPS_PACKET_LIST_IPSEC_INFORMATION0_
 - fwpsk/FWPS_PACKET_LIST_IPSEC_INFORMATION0_
 - FWPS_PACKET_LIST_IPSEC_INFORMATION0
 - fwpsk/FWPS_PACKET_LIST_IPSEC_INFORMATION0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fwpsk.h
api_name:
 - FWPS_PACKET_LIST_IPSEC_INFORMATION0
---

# FWPS_PACKET_LIST_IPSEC_INFORMATION0_ structure


## -description

The <b>FWPS_PACKET_LIST_IPSEC_INFORMATION0</b> structure defines IPsec information associated with a packet
  list.
<div class="alert"><b>Note</b>  <b>FWPS_PACKET_LIST_IPSEC_INFORMATION0</b> is a specific version of <b>FWPS_PACKET_LIST_IPSEC_INFORMATION</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -struct-fields

### -field inbound

An 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_packet_list_inbound_ipsec_information0_">FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0</a> structure that contains IPsec information associated
      with inbound packet data.

### -field outbound

An 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_packet_list_outbound_ipsec_information0_">FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0</a> structure that contains IPsec information associated
      with outbound packet data.

### -field flags

A value that contains a generic representation of the IPsec information associated with the
      packet list.

## -remarks

A FWPS_PACKET_LIST_IPSEC_INFORMATION0 structure is included as a member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_packet_list_information0_">
    FWPS_PACKET_LIST_INFORMATION0</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_packet_list_inbound_ipsec_information0_">
   FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_packet_list_information0_">FWPS_PACKET_LIST_INFORMATION0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_packet_list_outbound_ipsec_information0_">
   FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0</a>

