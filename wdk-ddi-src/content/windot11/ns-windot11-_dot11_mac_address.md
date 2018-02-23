---
UID: NS:windot11._DOT11_MAC_ADDRESS
title: "_DOT11_MAC_ADDRESS"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_mac_address.htm
old-project: netvista
ms.assetid: 6b2b17fd-3695-4598-8d9a-be28e1bc5b53
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11_MAC_ADDRESS, PDOT11_MAC_ADDRESS, Native_802.11_data_types_8ff45785-198d-48f0-99b5-b79a27753668.xml, *PDOT11_MAC_ADDRESS, netvista.dot11_mac_address, PDOT11_MAC_ADDRESS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_MAC_ADDRESS, windot11/DOT11_MAC_ADDRESS, DOT11_MAC_ADDRESS structure [Network Drivers Starting with Windows Vista], windot11/PDOT11_MAC_ADDRESS
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
</table></span></div>
A multicast MAC address uniquely identifies a group of stations on a WLAN. A MAC address is defined as
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
</table></span></div>
A broadcast MAC address identifies all stations on a WLAN. The broadcast MAC address is
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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569419">OID_DOT11_STATION_ID</a>



<a href="..\windot11\ns-windot11-dot11_disassociation_parameters.md">
   DOT11_DISASSOCIATION_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_stop_post_associate.md">
   Dot11ExtIhvStopPostAssociate</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-roaming-start">NDIS_STATUS_DOT11_ROAMING_START</a>



<a href="..\windot11\ns-windot11-dot11_cipher_default_key_value.md">
   DOT11_CIPHER_DEFAULT_KEY_VALUE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567344">NDIS_STATUS_DOT11_LINK_QUALITY</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-excluded-mac-address-list">
   OID_DOT11_EXCLUDED_MAC_ADDRESS_LIST</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_post_associate_completion.md">
   Dot11ExtPostAssociateCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569360">OID_DOT11_ENUM_BSS_LIST</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-association-start">
   NDIS_STATUS_DOT11_ASSOCIATION_START</a>



<a href="..\windot11\ns-windot11-dot11_association_completion_parameters.md">
   DOT11_ASSOCIATION_COMPLETION_PARAMETERS</a>



<a href="..\windot11\ns-windot11-dot11_bss_entry.md">DOT11_BSS_ENTRY</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-desired-bssid-list">OID_DOT11_DESIRED_BSSID_LIST</a>



<a href="..\wlclient\ns-wlclient-_dot11_port_state.md">DOT11_PORT_STATE</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn305127">
   NDIS_STATUS_DOT11_CONNECTION_START</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-disassociation">
   NDIS_STATUS_DOT11_DISASSOCIATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569359">OID_DOT11_ENUM_ASSOCIATION_INFO</a>



<a href="..\windot11\ns-windot11-_dot11_scan_request_v2.md">DOT11_SCAN_REQUEST_V2</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-cipher-key-mapping-key">
   OID_DOT11_CIPHER_KEY_MAPPING_KEY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a>



<a href="..\windot11\ns-windot11-dot11_roaming_completion_parameters.md">
   DOT11_ROAMING_COMPLETION_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569400">OID_DOT11_PMKID_LIST</a>



<a href="https://msdn.microsoft.com/en-us/library/gg157151.aspx">
   NDIS_STATUS_DOT11_TKIPMIC_FAILURE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569125">OID_DOT11_CURRENT_ADDRESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_MAC_ADDRESS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

