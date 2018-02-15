---
UID: NC:ndis.NDIS_SWITCH_REFERENCE_SWITCH_NIC
title: NDIS_SWITCH_REFERENCE_SWITCH_NIC
author: windows-driver-content
description: The ReferenceSwitchNic function increments the Hyper-V extensible switch reference counter for a network adapter that is connected to an extensible switch port.
old-location: netvista\ReferenceSwitchNic.htm
old-project: netvista
ms.assetid: 8F4C76FA-A386-4A3D-8C9F-3CFF69382702
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ReferenceSwitchNic, ReferenceSwitchNic callback function [Network Drivers Starting with Windows Vista], ReferenceSwitchNic, NDIS_SWITCH_REFERENCE_SWITCH_NIC, NDIS_SWITCH_REFERENCE_SWITCH_NIC, ndis/ReferenceSwitchNic
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndis.h
apiname:
-	ReferenceSwitchNic
product: Windows
targetos: Windows
req.typenames: "*LPVIDEO_STREAM_INIT_PARMS, VIDEO_STREAM_INIT_PARMS"
---

# NDIS_SWITCH_REFERENCE_SWITCH_NIC callback


## -description



The <i>ReferenceSwitchNic</i> function increments the Hyper-V extensible switch reference counter for a network adapter that is connected to an extensible switch port.




## -prototype


````
NDIS_SWITCH_REFERENCE_SWITCH_NIC ReferenceSwitchNic;

NDIS_STATUS ReferenceSwitchNic(
  _In_ NDIS_SWITCH_CONTEXT   NdisSwitchContext,
  _In_ NDIS_SWITCH_PORT_ID   SwitchPortId,
  _In_ NDIS_SWITCH_NIC_INDEX SwitchNicIndex
)
{ ... }
````


## -parameters




### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the  extension calls <a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param SwitchPortId [in]

An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port  to which the virtual network adapter is connected.


### -param SwitchNicIndex [in]

An NDIS_SWITCH_NIC_INDEX value that specifies the index of the virtual network adapter for which the extensible switch reference counter is to be incremented.

For more information on NDIS_SWITCH_NIC_INDEX values, see <a href="https://msdn.microsoft.com/969333DA-0282-474B-8D56-72CD623C5329">Network Adapter Index Values</a>.

<div class="alert"><b>Note</b>  This parameter must specify the index value of a network adapter that is in a connected state. Index values for network adapters that are in a created or disconnected state cannot be specified. For more information about network connection states, see <a href="https://msdn.microsoft.com/1E2075E3-D7CC-4364-ABB2-D5969DB361B5">Hyper-V Extensible Switch Port and Network Adapter States</a>.</div>
<div> </div>

## -returns



If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.






## -remarks



The extensible switch extension calls <i>ReferenceSwitchNic</i> to increment a reference counter for a network adapter that is connected to an extensible switch port. While the reference counter has a nonzero value, the protocol edge of the extensible switch will not issue an object identifier (OID) set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598264">OID_SWITCH_NIC_DELETE</a> to delete the connection to the adapter. 

After the extension calls <i>ReferenceSwitchNic</i>, it must call <a href="https://msdn.microsoft.com/58C72F81-07B9-45FE-A8BA-0405DBE4CA20">DereferenceSwitchNic</a> to decrement the extensible switch reference counter. 

The extension  should call <i>ReferenceSwitchNic</i> before it performs the following operations:

<ul>
<li>
Forwards an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598266">OID_SWITCH_NIC_REQUEST</a> OID request over the extensible switch control path to an underlying physical network adapter. 


For more information, see <a href="https://msdn.microsoft.com/7E828FA8-DE99-4C30-ABB6-8AF05F9EC3B7">Managing OID Requests to Physical Network Adapters</a>.

</li>
<li>
Forwards an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598205">NDIS_STATUS_SWITCH_NIC_STATUS</a> status indication over the extensible switch control path from an underlying external adapter.

For more information, see <a href="https://msdn.microsoft.com/ECA336FD-3E07-47D8-9006-6FE9CC1BEC2F">Managing NDIS Status Indications from Physical Network Adapters</a>.

</li>
</ul>
<div class="alert"><b>Note</b>  The extension must not call <i>ReferenceSwitchNic</i> when forwarding packets over the extensible switch data path. The extensible switch interface manages its own reference counters for packets that are forwarded to ports and network adapter connections over the data path.</div>
<div> </div>
The extension calls <i>ReferenceSwitchNic</i> after the network adapter connection has reached the <i>Network adapter connection created</i> state. The extension must not call <i>ReferenceSwitchNic</i> after the connection has reached the <i>Network adapter disconnected</i> or <i>Network adapter deleted</i> states. For more information about these states, see <a href="https://msdn.microsoft.com/1E2075E3-D7CC-4364-ABB2-D5969DB361B5">Hyper-V Extensible Switch Port and Network Adapter States</a>.

<div class="alert"><b>Note</b>  When the extension calls <i>ReferenceSwitchNic</i>, it does not have to synchronize the call with its code that handles OID requests. As a result, it is possible for the extension to call <i>ReferenceSwitchNic</i> while the protocol edge of the extensible switch issues an OID request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598265">OID_SWITCH_NIC_DISCONNECT</a>. However, if the call to <i>ReferenceSwitchNic</i> completes with NDIS_STATUS_SUCCESS, the extension can still forward <a href="https://msdn.microsoft.com/library/windows/hardware/hh598266">OID_SWITCH_NIC_REQUEST</a> OID request or <a href="https://msdn.microsoft.com/library/windows/hardware/hh598205">NDIS_STATUS_SWITCH_NIC_STATUS</a> status indications after it handles the OID_SWITCH_NIC_DISCONNECT OID request.</div>
<div> </div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598264">OID_SWITCH_NIC_DELETE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598266">OID_SWITCH_NIC_REQUEST</a>



<a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598205">NDIS_STATUS_SWITCH_NIC_STATUS</a>



<a href="https://msdn.microsoft.com/58C72F81-07B9-45FE-A8BA-0405DBE4CA20">DereferenceSwitchNic</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598265">OID_SWITCH_NIC_DISCONNECT</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_REFERENCE_SWITCH_NIC callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

