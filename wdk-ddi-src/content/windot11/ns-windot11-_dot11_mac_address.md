---
UID: NS:windot11._DOT11_MAC_ADDRESS
title: "_DOT11_MAC_ADDRESS"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_mac_address.htm
old-project: netvista
ms.assetid: 6b2b17fd-3695-4598-8d9a-be28e1bc5b53
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: windot11/DOT11_MAC_ADDRESS, DOT11_MAC_ADDRESS structure [Network Drivers Starting with Windows Vista], PDOT11_MAC_ADDRESS, *PDOT11_MAC_ADDRESS, Native_802.11_data_types_8ff45785-198d-48f0-99b5-b79a27753668.xml, windot11/PDOT11_MAC_ADDRESS, netvista.dot11_mac_address, PDOT11_MAC_ADDRESS structure pointer [Network Drivers Starting with Windows Vista], DOT11_MAC_ADDRESS, _DOT11_MAC_ADDRESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
-	DOT11_MAC_ADDRESS
product: Windows
targetos: Windows
req.typenames: DOT11_MAC_ADDRESS, *PDOT11_MAC_ADDRESS
req.product: Windows 10 or later.
---

# _DOT11_MAC_ADDRESS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The 
  <b>DOT11_MAC_ADDRESS</b> array defines an IEEE media access control (MAC) address.


## -syntax


````
typedef struct _DOT11_MAC_ADDRESS {
  UCHAR ucDot11MacAddress[6];
} DOT11_MAC_ADDRESS, *PDOT11_MAC_ADDRESS;
````


## -struct-fields




### -field ucDot11MacAddress

The MAC address in unicast, multicast, or broadcast format.


## -remarks


A unicast MAC address uniquely identifies a station on a WLAN. A MAC address is defined as a unicast
    address if the following is true:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>(DOT11_MAC_ADDRESS[0] &amp; 0x01 == 0)</pre>
</td>
</tr>
</table></span></div>A multicast MAC address uniquely identifies a group of stations on a WLAN. A MAC address is defined as
    a multicast address if the following is true:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>(DOT11_MAC_ADDRESS[0] &amp; 0x01 == 1)</pre>
</td>
</tr>
</table></span></div>A broadcast MAC address identifies all stations on a WLAN. The broadcast MAC address is
    0xFFFFFFFFFFFF.

The PDOT11_MAC_ADDRESS type is defined as a pointer to the DOT11_MAC_ADDRESS type as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef DOT11_MAC_ADDRESS  *PDOT11_MAC_ADDRESS;</pre>
</td>
</tr>
</table></span></div>


## -see-also

<a href="..\windot11\ns-windot11-dot11_bss_entry.md">DOT11_BSS_ENTRY</a>

<mshelp:link keywords="netvista.dot11extpostassociatecompletion" tabindex="0"><i>
   Dot11ExtPostAssociateCompletion</i></mshelp:link>

<mshelp:link keywords="netvista.oid_dot11_excluded_mac_address_list" tabindex="0">
   OID_DOT11_EXCLUDED_MAC_ADDRESS_LIST</mshelp:link>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569360">OID_DOT11_ENUM_BSS_LIST</a>

<mshelp:link keywords="netvista.ndis_status_dot11_disassociation" tabindex="0">
   NDIS_STATUS_DOT11_DISASSOCIATION</mshelp:link>

<a href="..\wlclient\ns-wlclient-_dot11_port_state.md">DOT11_PORT_STATE</a>

<mshelp:link keywords="netvista.dot11_roaming_completion_parameters" tabindex="0"><b>
   DOT11_ROAMING_COMPLETION_PARAMETERS</b></mshelp:link>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567360">NDIS_STATUS_DOT11_ROAMING_START</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569359">OID_DOT11_ENUM_ASSOCIATION_INFO</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569125">OID_DOT11_CURRENT_ADDRESS</a>

<mshelp:link keywords="netvista.ndis_status_dot11_connection_start" tabindex="0">
   NDIS_STATUS_DOT11_CONNECTION_START</mshelp:link>

<mshelp:link keywords="netvista.ndis_status_dot11_tkipmic_failure" tabindex="0">
   NDIS_STATUS_DOT11_TKIPMIC_FAILURE</mshelp:link>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567344">NDIS_STATUS_DOT11_LINK_QUALITY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569400">OID_DOT11_PMKID_LIST</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-desired-bssid-list">OID_DOT11_DESIRED_BSSID_LIST</a>

<mshelp:link keywords="netvista.ndis_status_dot11_association_start" tabindex="0">
   NDIS_STATUS_DOT11_ASSOCIATION_START</mshelp:link>

<mshelp:link keywords="netvista.dot11_cipher_default_key_value" tabindex="0"><b>
   DOT11_CIPHER_DEFAULT_KEY_VALUE</b></mshelp:link>

<mshelp:link keywords="netvista.dot11_association_completion_parameters" tabindex="0"><b>
   DOT11_ASSOCIATION_COMPLETION_PARAMETERS</b></mshelp:link>

<mshelp:link keywords="netvista.dot11_disassociation_parameters" tabindex="0"><b>
   DOT11_DISASSOCIATION_PARAMETERS</b></mshelp:link>

<a href="..\windot11\ns-windot11-_dot11_scan_request_v2.md">DOT11_SCAN_REQUEST_V2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569419">OID_DOT11_STATION_ID</a>

<mshelp:link keywords="netvista.dot11extihvstoppostassociate" tabindex="0"><i>
   Dot11ExtIhvStopPostAssociate</i></mshelp:link>

<mshelp:link keywords="netvista.oid_dot11_cipher_key_mapping_key" tabindex="0">
   OID_DOT11_CIPHER_KEY_MAPPING_KEY</mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_MAC_ADDRESS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

