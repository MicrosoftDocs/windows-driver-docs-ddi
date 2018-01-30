---
UID: NS:windot11._DOT11_WFD_GROUP_JOIN_PARAMETERS
title: "_DOT11_WFD_GROUP_JOIN_PARAMETERS"
author: windows-driver-content
description: The DOT11_WFD_GROUP_JOIN_PARAMETERS structure is included with an OID_DOT11_WFD_GROUP_JOIN_PARAMETERS request. The structure contains startup parameters for a Client.
old-location: netvista\dot11_wfd_group_join_parameters.htm
old-project: netvista
ms.assetid: 7E526179-97B6-4BA3-8F78-C4C04FFF9085
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: windot11/DOT11_WFD_GROUP_JOIN_PARAMETERS, PDOT11_WFD_GROUP_JOIN_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_GROUP_JOIN_PARAMETERS, DOT11_WFD_GROUP_JOIN_PARAMETERS, DOT11_WFD_GROUP_JOIN_PARAMETERS structure [Network Drivers Starting with Windows Vista], *PDOT11_WFD_GROUP_JOIN_PARAMETERS, PDOT11_WFD_GROUP_JOIN_PARAMETERS, windot11/PDOT11_WFD_GROUP_JOIN_PARAMETERS, netvista.dot11_wfd_group_join_parameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8.
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
-	Windot11.h
apiname:
-	DOT11_WFD_GROUP_JOIN_PARAMETERS
product: Windows
targetos: Windows
req.typenames: "*PDOT11_WFD_GROUP_JOIN_PARAMETERS, DOT11_WFD_GROUP_JOIN_PARAMETERS"
req.product: Windows 10 or later.
---

# _DOT11_WFD_GROUP_JOIN_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_WFD_GROUP_JOIN_PARAMETERS</b> structure is included with an <a href="https://msdn.microsoft.com/8BA9DC85-41DA-4021-BFBC-2C64A38146E9">OID_DOT11_WFD_GROUP_JOIN_PARAMETERS</a> request. The structure contains startup parameters for a Client.


## -syntax


````
typedef struct _DOT11_WFD_GROUP_JOIN_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_WFD_CHANNEL  GOOperatingChannel;
  ULONG              GOConfigTime;
  BOOLEAN            bInGroupFormation;
  BOOLEAN            bWaitForWPSReady;
} DOT11_WFD_GROUP_JOIN_PARAMETERS, *PDOT11_WFD_GROUP_JOIN_PARAMETERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>DOT11_WFD_GROUP_JOIN_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following.
<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_ GROUP_JOIN_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_WFD_GROUP_JOIN_PARAMETERS_REVISION_1</td>
</tr>
</table> 


### -field GOOperatingChannel

This channel on which the Group Owner (GO) may operate the group. This channel information was received by the Client in a GO Negotiation or Invitation exchange. The miniport must also be able to handle the group operating on a channel different than specified. The miniport must ensure regulatory compliance when joining the group.


### -field GOConfigTime

The configuration time allowed for the GO to start. This time-out is received by the Client in a GO Negotiation or Invitation exchange.


### -field bInGroupFormation

If set to TRUE, special handling of <a href="https://msdn.microsoft.com/67B02FD9-1CB2-424D-989C-11A307070B93">OID_DOT11_WFD_CONNECT_TO_GROUP_REQUEST</a> is required. The miniport must not attempt to connect until it receives a probe response or beacon from the GO with the Group Formation field set to 1. Otherwise, no connect delay is necessary.


### -field bWaitForWPSReady

If set to TRUE, special handling of <a href="https://msdn.microsoft.com/67B02FD9-1CB2-424D-989C-11A307070B93">OID_DOT11_WFD_CONNECT_TO_GROUP_REQUEST</a> is required. The miniport must not attempt to connect until it receives a probe response or beacon from the GO with the Selected Registrar WPS attribute set to TRUE and the Group Formation field set to the  value indicated by <b>bInGroupFormation</b>. Otherwise, the Selected Registrar attribute should be ignored.


## -see-also

<a href="https://msdn.microsoft.com/8BA9DC85-41DA-4021-BFBC-2C64A38146E9">OID_DOT11_WFD_GROUP_JOIN_PARAMETERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_WFD_GROUP_JOIN_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

