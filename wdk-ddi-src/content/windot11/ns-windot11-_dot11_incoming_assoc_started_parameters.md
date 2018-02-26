---
UID: NS:windot11._DOT11_INCOMING_ASSOC_STARTED_PARAMETERS
title: "_DOT11_INCOMING_ASSOC_STARTED_PARAMETERS"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_incoming_assoc_started_parameters.htm
old-project: netvista
ms.assetid: 8bf8d69a-0c47-48c1-83f5-d436a3ab8323
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PDOT11_INCOMING_ASSOC_STARTED_PARAMETERS, ,, 1, A, C, D, DOT11_INCOMING_ASSOC_STARTED_PARAMETERS, DOT11_INCOMING_ASSOC_STARTED_PARAMETERS structure [Network Drivers Starting with Windows Vista], E, G, I, M, N, Native_802.11_data_types_f09f57cb-9f15-444c-b09f-d97f016e86a2.xml, O, P, PDOT11_INCOMING_ASSOC_STARTED_PARAMETERS, PDOT11_INCOMING_ASSOC_STARTED_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], R, S, T, _, _DOT11_INCOMING_ASSOC_STARTED_PARAMETERS, netvista.dot11_incoming_assoc_started_parameters, windot11/DOT11_INCOMING_ASSOC_STARTED_PARAMETERS, windot11/PDOT11_INCOMING_ASSOC_STARTED_PARAMETERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	windot11.h
apiname:
-	DOT11_INCOMING_ASSOC_STARTED_PARAMETERS
product: Windows
targetos: Windows
req.typenames: DOT11_INCOMING_ASSOC_STARTED_PARAMETERS, *PDOT11_INCOMING_ASSOC_STARTED_PARAMETERS
req.product: Windows 10 or later.
---

# _DOT11_INCOMING_ASSOC_STARTED_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_INCOMING_ASSOC_STARTED_PARAMETERS structure specifies that the NIC has received the first
  valid 802.11 authentication request from a peer station on an infrastructure BSS.


## -syntax


````
typedef struct _DOT11_INCOMING_ASSOC_STARTED_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  PeerMacAddr;
} DOT11_INCOMING_ASSOC_STARTED_PARAMETERS, *PDOT11_INCOMING_ASSOC_STARTED_PARAMETERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_INCOMING_ASSOC_STARTED_PARAMETERS structure. This member
     is formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:



<table>
<tr>
<th>Term</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<a id="Type"></a><a id="type"></a><a id="TYPE"></a>Type

</td>
<td width="60%">
This member must be set to NDIS_OBJECT_TYPE_DEFAULT.

</td>
</tr>
<tr>
<td width="40%">
<a id="Revision"></a><a id="revision"></a><a id="REVISION"></a>Revision

</td>
<td width="60%">
This member must be set to DOT11_INCOMING_ASSOC_STARTED_PARAMETERS_REVISION_1.

</td>
</tr>
<tr>
<td width="40%">
<a id="Size"></a><a id="size"></a><a id="SIZE"></a>Size

</td>
<td width="60%">
This member must be set to 
       <b>sizeof</b>(DOT11_INCOMING_ASSOC_STARTED_PARAMETERS).

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field PeerMacAddr

The media access control (MAC) address of the peer station that sent an 802.11 authentication
     request.


## -remarks



The Native 802.11 miniport driver includes a DOT11_INCOMING_ASSOC_STARTED_PARAMETERS structure when
    the driver makes an 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-incoming-assoc-started">
    NDIS_STATUS_DOT11_INCOMING_ASSOC_STARTED</a> status indication.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-incoming-assoc-started">
   NDIS_STATUS_DOT11_INCOMING_ASSOC_STARTED</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_INCOMING_ASSOC_STARTED_PARAMETERS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

