---
UID: NF:fwpsk.FwpsQueryPacketInjectionState0
title: FwpsQueryPacketInjectionState0 function
author: windows-driver-content
description: The FwpsQueryPacketInjectionState0 function is called by a callout to query the injection state of packet data.Note  FwpsQueryPacketInjectionState0 is a specific version of FwpsQueryPacketInjectionState.
old-location: netvista\fwpsquerypacketinjectionstate0.htm
old-project: netvista
ms.assetid: 785d99a5-a8c9-4763-bdd4-e26f604f6be7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FwpsQueryPacketInjectionState0, wfp_ref_2_funct_3_fwps_J-Q_2eb3c709-15f8-46de-a55d-b4e99c085740.xml, netvista.fwpsquerypacketinjectionstate0, FwpsQueryPacketInjectionState0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsQueryPacketInjectionState0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	fwpkclnt.lib
-	fwpkclnt.dll
apiname:
-	FwpsQueryPacketInjectionState0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsQueryPacketInjectionState0 function


## -description


The 
  <b>FwpsQueryPacketInjectionState0</b> function is called by a callout to query the injection state of packet
  data.
<div class="alert"><b>Note</b>  <b>FwpsQueryPacketInjectionState0</b> is a specific version of <b>FwpsQueryPacketInjectionState</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
FWPS_PACKET_INJECTION_STATE NTAPI FwpsQueryPacketInjectionState0(
  _In_            HANDLE          injectionHandle,
  _In_      const NET_BUFFER_LIST *netBufferList,
  _Out_opt_       HANDLE          *injectionContext
);
````


## -parameters




### -param injectionHandle [in]

An injection handle that was previously created by a call to the 
     <a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">
     FwpsInjectionHandleCreate0</a> function.


### -param netBufferList [in]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that describes
     the packet data that is being classified. The packet can originate from the network stack, or it can be
     injected into the network stack by a WFP callout driver.


### -param injectionContext [out, optional]

An optional handle to the injection context. If the pointer is specified, and if the packet
     injection state 
     <a href="..\fwpsk\ne-fwpsk-fwps_packet_injection_state_.md">FWPS_PACKET_INJECTION_STATE</a> associated with the injection handle is FWPS_PACKET_INJECTED_BY_SELF
     or FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF, the injection context supplied when the packet was injected
     will be returned.


## -returns



The 
     <b>FwpsQueryPacketInjectionState0</b> function returns one of the constant values of the 
     <a href="..\fwpsk\ne-fwpsk-fwps_packet_injection_state_.md">FWPS_PACKET_INJECTION_STATE</a> enumeration.




## -remarks



Because injected packet data can be reclassified against the callout that injected it, this function
    allows a callout to inspect the injection history of packet data when necessary, thereby avoiding the
    need to make repeated inspections of packet data that has already been inspected.

A callout can track other callout-specific information by specifying the optional 
    <i>injectionContext</i> handle in one of the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">packet injection functions</a> at the
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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a> structure pointed to
    by the 
    <i>classifyOut</i> parameter of the 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> function to one of the following
    values.






## -see-also

<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>



<a href="..\fwpsk\ne-fwpsk-fwps_packet_injection_state_.md">FWPS_PACKET_INJECTION_STATE</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">FwpsInjectionHandleCreate0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsQueryPacketInjectionState0 function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

