---
UID: NF:fwpsk.FwpsGetPacketListSecurityInformation0
title: FwpsGetPacketListSecurityInformation0 function
author: windows-driver-content
description: The FwpsGetPacketListSecurityInformation0 function retrieves information associated with a packet list.Note  FwpsGetPacketListSecurityInformation0 is a specific version of FwpsGetPacketListSecurityInformation.
old-location: netvista\fwpsgetpacketlistsecurityinformation0.htm
old-project: netvista
ms.assetid: c3391615-963b-4916-9280-ce782269692c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FwpsGetPacketListSecurityInformation0, FwpsGetPacketListSecurityInformation0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsGetPacketListSecurityInformation0, netvista.fwpsgetpacketlistsecurityinformation0, wfp_ref_2_funct_3_fwps_D-H_1c333aca-c13e-449e-b230-a6d217442a5d.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsGetPacketListSecurityInformation0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsGetPacketListSecurityInformation0 function


## -description


The 
  <b>FwpsGetPacketListSecurityInformation0</b> function retrieves information associated with a packet
  list.
<div class="alert"><b>Note</b>  <b>FwpsGetPacketListSecurityInformation0</b> is a specific version of <b>FwpsGetPacketListSecurityInformation</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS NTAPI FwpsGetPacketListSecurityInformation0(
  _In_    NET_BUFFER_LIST               *packetList,
  _In_    UINT32                        queryFlags,
  _Inout_ FWPS_PACKET_LIST_INFORMATION0 *packetInformation
);
````


## -parameters




### -param packetList [in]

A pointer to the 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure for which the
     associated information is being retrieved.


### -param queryFlags [in]

A UINT32 value that contains a bitwise OR of a combination of the following flags that specify the
     information to be retrieved:
     





#### FWPS_PACKET_LIST_INFORMATION_QUERY_INBOUND

Retrieve information for an inbound packet list.



#### FWPS_PACKET_LIST_INFORMATION_QUERY_OUTBOUND

Retrieve information for an outbound packet list.



#### FWPS_PACKET_LIST_INFORMATION_QUERY_IPSEC

Retrieve the IPsec information associated with the packet list. This flag must be used in
       combination with either the FWPS_PACKET_LIST_INFORMATION_QUERY_INBOUND flag or the
       FWPS_PACKET_LIST_INFORMATION_QUERY_OUTBOUND flag.



#### FWPS_PACKET_LIST_INFORMATION_QUERY_FWP

Retrieve the Windows Filtering Platform information associated with the packet list.



#### FWPS_PACKET_LIST_INFORMATION_QUERY_ALL_INBOUND

Retrieve all information associated with an inbound packet list.



#### FWPS_PACKET_LIST_INFORMATION_QUERY_ALL_OUTBOUND

Retrieve all information associated with an outbound packet list.


### -param packetInformation [in, out]

A pointer to an 
     <a href="..\fwpsk\ns-fwpsk-fwps_packet_list_information0_.md">FWPS_PACKET_LIST_INFORMATION0</a> structure that receives the information associated with the packet
     list.


## -returns



The 
     <b>FwpsGetPacketListSecurityInformation0</b> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The information associated with the packet list was successfully retrieved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>
 




## -remarks



A callout driver calls the 
    <b>FwpsGetPacketListSecurityInformation0</b> function from within its 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function to retrieve
    information associated with the packet list. This information can be used to determine the action to be
    taken on the data.




## -see-also

<a href="..\fwpsk\ns-fwpsk-fwps_packet_list_information0_.md">FWPS_PACKET_LIST_INFORMATION0</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsGetPacketListSecurityInformation0 function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

