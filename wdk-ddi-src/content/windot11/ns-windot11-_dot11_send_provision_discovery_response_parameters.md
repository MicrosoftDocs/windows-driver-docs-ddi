---
UID: NS:windot11._DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS
title: "_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS"
author: windows-driver-content
description: The parameters for a response to a provision discovery request are specified in a DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS structure. This structure is sent with an OID_DOT11_WFD_SEND_PROVISION_DISCOVERY_RESPONSE request to the miniport.
old-location: netvista\dot11_send_provision_discovery_response_parameters.htm
old-project: netvista
ms.assetid: C6F937B8-6C3B-4D95-ADE0-931463EB57C3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PDOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, ,, 1, A, C, D, DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS structure [Network Drivers Starting with Windows Vista], E, I, M, N, O, P, PDOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, PDOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], R, S, T, V, Y, _, _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, netvista.dot11_send_provision_discovery_response_parameters, windot11/DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, windot11/PDOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
-	DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS
product: Windows
targetos: Windows
req.typenames: DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, *PDOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS
req.product: Windows 10 or later.
---

# _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The parameters for a response to a provision discovery request are specified in a <b>DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS</b> structure. This structure is sent with an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451808">OID_DOT11_WFD_SEND_PROVISION_DISCOVERY_RESPONSE</a> request to the miniport.


## -syntax


````
typedef struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  ReceiverDeviceAddress;
  DOT11_DIALOG_TOKEN DialogToken;
  PVOID              RequestContext;
  ULONG              uSendTimeout;
  ULONG              uIEsOffset;
  ULONG              uIEsLength;
} DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, *PDOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following.

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
<td>DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_REVISION_1</td>
</tr>
</table>
 


### -field ReceiverDeviceAddress

The address of the device that transmitted the provision discovery request packet.


### -field DialogToken

The dialog token received from the provision discovery request packet. This token must be used in the provision discovery response packet.


### -field RequestContext

The context data given initially by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439797">NDIS_STATUS_DOT11_WFD_RECEIVED_PROVISION_DISCOVERY_REQUEST</a> indication.


### -field uSendTimeout

The maximum time, in milliseconds, allowed to send the provision discovery response. If the time-out expires before the miniport has successfully transmitted the provision discovery response, it should indicate the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439785">NDIS_STATUS_DOT11_WFD_PROVISION_DISCOVERY_RESPONSE_SEND_COMPLETE</a> with a failure status.


### -field uIEsOffset

The offset, in bytes,  of the array of additional information elements (IEs) the Wi-Fi Direct (WFD) port must add to the provision discovery response packet. This offset is from the start of the buffer that contains this structure.


### -field uIEsLength

The length, in bytes, of the array of IEs provided at <b>uIEsOffset</b>.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451808">OID_DOT11_WFD_SEND_PROVISION_DISCOVERY_RESPONSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439785">NDIS_STATUS_DOT11_WFD_PROVISION_DISCOVERY_RESPONSE_SEND_COMPLETE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439797">NDIS_STATUS_DOT11_WFD_RECEIVED_PROVISION_DISCOVERY_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

