---
UID: NS:windot11.DOT11_ROAMING_START_PARAMETERS
title: DOT11_ROAMING_START_PARAMETERS
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_roaming_start_parameters.htm
old-project: netvista
ms.assetid: 23a0eabc-9eac-4375-b2ca-66b70deaba82
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PDOT11_ROAMING_START_PARAMETERS, ,, 1, A, D, DOT11_ROAMING_START_PARAMETERS, DOT11_ROAMING_START_PARAMETERS structure [Network Drivers Starting with Windows Vista], E, G, I, M, N, Native_802.11_data_types_7635397d-74dc-44d0-af58-47048361367d.xml, O, P, PDOT11_ROAMING_START_PARAMETERS, PDOT11_ROAMING_START_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], R, S, T, _, netvista.dot11_roaming_start_parameters, windot11/DOT11_ROAMING_START_PARAMETERS, windot11/PDOT11_ROAMING_START_PARAMETERS"
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
-	DOT11_ROAMING_START_PARAMETERS
product: Windows
targetos: Windows
req.typenames: DOT11_ROAMING_START_PARAMETERS, *PDOT11_ROAMING_START_PARAMETERS
req.product: Windows 10 or later.
---

# DOT11_ROAMING_START_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_ROAMING_START_PARAMETERS structure specifies the reason why the Native 802.11 miniport
  driver is performing a roaming operation. The driver includes a DOT11_ROAMING_START_PARAMETERS structure
  when the driver makes an 
  <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-roaming-start">
  NDIS_STATUS_DOT11_ROAMING_START</a> status indication.


## -syntax


````
typedef struct DOT11_ROAMING_START_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  AdhocBSSID;
  DOT11_SSID         AdhocSSID;
  DOT11_ASSOC_STATUS uRoamingReason;
} DOT11_ROAMING_START_PARAMETERS, *PDOT11_ROAMING_START_PARAMETERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_ROAMING_START_PARAMETERS structure. This member is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_ROAMING_START_PARAMETERS_REVISION_1.



#### Size

This member must be set to 
       sizeof(DOT11_ROAMING_START_PARAMETERS).

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field AdhocBSSID

If the IEEE 802.11 
     <b>dot11DesiredBSSType</b> MIB object is set to 
     <b>dot11_BSS_type_independent</b>, the 
     <b>AdhocBSSID</b> member contains the basic service set (BSS) identifier (BSSID) of the independent BSS
     (IBSS) network that the 802.11 station is attempting to roam to.

<div class="alert"><b>Note</b>  IBSS (Ad hoc) and SoftAP are deprecated. Starting with Windows 8.1 and Windows Server 2012 R2, use <a href="https://msdn.microsoft.com/library/windows/hardware/mt244265">Wi-Fi Direct</a>.</div>
<div> </div>
If the 
     <b>dot11DesiredBSSType</b> MIB object is set to 
     <b>dot11_BSS_type_infrastructure</b>, the miniport driver must fill 
     <b>AdhocBSSID</b> with zeros.

For more information about the data type for this member, see 
     <a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a>.


### -field AdhocSSID

If the 
     <b>dot11DesiredBSSType</b> MIB object is set to 
     <b>dot11_BSS_type_independent</b>, the 
     <b>AdhocSSID</b> member contains the service set identifier (SSID) of the IBSS network that the 802.11
     station is attempting to roam to.

<div class="alert"><b>Note</b>  IBSS (Ad hoc) and SoftAP are deprecated. Starting with Windows 8.1 and Windows Server 2012 R2, use <a href="https://msdn.microsoft.com/library/windows/hardware/mt244265">Wi-Fi Direct</a>.</div>
<div> </div>
If the 
     <b>dot11DesiredBSSType</b> MIB object is set to 
     <b>dot11_BSS_type_infrastructure</b>, the miniport driver must fill 
     <b>AdhocSSID</b> with zeros.

For more information about the data type for this member, see 
     <a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a>.

For more information about the IEEE 802.11 
     <b>dot11DesiredBSSType</b> MIB object, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-desired-bss-type">
     OID_DOT11_DESIRED_BSS_TYPE</a>.


### -field uRoamingReason

The reason that the 802.11 station is roaming, which is formatted as a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff547652">DOT11_ASSOC_STATUS</a> value.


## -remarks



For more information about the roaming operation, see 
    <a href="https://msdn.microsoft.com/b52e134e-4f26-4797-af57-dd7da177c193">Roaming Operations</a>.




## -see-also

<a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547652">DOT11_ASSOC_STATUS</a>



<a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-desired-bss-type">OID_DOT11_DESIRED_BSS_TYPE</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-roaming-start">NDIS_STATUS_DOT11_ROAMING_START</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_ROAMING_START_PARAMETERS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

