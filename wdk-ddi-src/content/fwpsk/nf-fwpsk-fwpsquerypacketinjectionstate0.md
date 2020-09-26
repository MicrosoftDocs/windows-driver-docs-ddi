---
UID: NF:fwpsk.FwpsQueryPacketInjectionState0
title: FwpsQueryPacketInjectionState0 function (fwpsk.h)
description: The FwpsQueryPacketInjectionState0 function is called by a callout to query the injection state of packet data.Note  FwpsQueryPacketInjectionState0 is a specific version of FwpsQueryPacketInjectionState.
old-location: netvista\fwpsquerypacketinjectionstate0.htm
tech.root: netvista
ms.assetid: 785d99a5-a8c9-4763-bdd4-e26f604f6be7
ms.date: 05/02/2018
keywords: ["FwpsQueryPacketInjectionState0 function"]
ms.keywords: FwpsQueryPacketInjectionState0, FwpsQueryPacketInjectionState0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsQueryPacketInjectionState0, netvista.fwpsquerypacketinjectionstate0, wfp_ref_2_funct_3_fwps_J-Q_2eb3c709-15f8-46de-a55d-b4e99c085740.xml
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpsQueryPacketInjectionState0
 - fwpsk/FwpsQueryPacketInjectionState0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsQueryPacketInjectionState0
---

# FwpsQueryPacketInjectionState0 function


## -description

The 
  <b>FwpsQueryPacketInjectionState0</b> function is called by a callout to query the injection state of packet
  data.
<div class="alert"><b>Note</b>  <b>FwpsQueryPacketInjectionState0</b> is a specific version of <b>FwpsQueryPacketInjectionState</b>. See <a href="/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters

### -param injectionHandle 

[in]
An injection handle that was previously created by a call to the 
     <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">
     FwpsInjectionHandleCreate0</a> function.

### -param netBufferList 

[in]
A pointer to a 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure that describes
     the packet data that is being classified. The packet can originate from the network stack, or it can be
     injected into the network stack by a WFP callout driver.

### -param injectionContext 

[out, optional]
An optional handle to the injection context. If the pointer is specified, and if the packet
     injection state 
     <a href="/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_packet_injection_state_">FWPS_PACKET_INJECTION_STATE</a> associated with the injection handle is FWPS_PACKET_INJECTED_BY_SELF
     or FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF, the injection context supplied when the packet was injected
     will be returned.

## -returns

The 
     <b>FwpsQueryPacketInjectionState0</b> function returns one of the constant values of the 
     <a href="/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_packet_injection_state_">FWPS_PACKET_INJECTION_STATE</a> enumeration.

## -remarks

Because injected packet data can be reclassified against the callout that injected it, this function
    allows a callout to inspect the injection history of packet data when necessary, thereby avoiding the
    need to make repeated inspections of packet data that has already been inspected.

A callout can track other callout-specific information by specifying the optional 
    <i>injectionContext</i> handle in one of the 
    <a href="/windows-hardware/drivers/network/packet-injection-functions">packet injection functions</a> at the
    time of packet data injection. If the 
    <b>FwpsQueryPacketInjectionState0</b> function returns <b>FWPS_PACKET_INJECTED_BY_SELF</b> or
    <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b>, the supplied 
    <i>injectionContext</i> will be returned as the 
    <i>completionContext</i> parameter of the function that performed the injection.

If the return value is <b>FWPS_PACKET_INJECTED_BY_SELF</b> or <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b>, the
    network buffer list pointed to by 
    <i>netBufferList</i> should not be further modified or pended as part of a cloning and injection
    procedure. In this case, the callout should set the 
    <b>actionType</b> member of the 
    <a href="/windows/win32/api/fwpstypes/ns-fwpstypes-fwps_classify_out0">FWPS_CLASSIFY_OUT0</a> structure pointed to
    by the 
    <i>classifyOut</i> parameter of the 
    <a href="/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> function to one of the following
    values.

## -see-also

<a href="/windows/win32/api/fwpstypes/ns-fwpstypes-fwps_classify_out0">FWPS_CLASSIFY_OUT0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_packet_injection_state_">FWPS_PACKET_INJECTION_STATE</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">FwpsInjectionHandleCreate0</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>