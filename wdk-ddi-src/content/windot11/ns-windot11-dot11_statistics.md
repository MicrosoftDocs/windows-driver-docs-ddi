---
UID: NS:windot11.DOT11_STATISTICS
title: DOT11_STATISTICS
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_statistics.htm
old-project: netvista
ms.assetid: 714ad442-596b-4e67-82ce-a50e1808a3af
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: DOT11_STATISTICS structure [Network Drivers Starting with Windows Vista], PDOT11_STATISTICS, *PDOT11_STATISTICS, Native_802.11_data_types_613cdf17-03f8-47df-963b-f64ce23031e9.xml, windot11/DOT11_STATISTICS, DOT11_STATISTICS, PDOT11_STATISTICS structure pointer [Network Drivers Starting with Windows Vista], windot11/PDOT11_STATISTICS, netvista.dot11_statistics
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
-	DOT11_STATISTICS
product: Windows
targetos: Windows
req.typenames: DOT11_STATISTICS, *PDOT11_STATISTICS
req.product: Windows 10 or later.
---

# DOT11_STATISTICS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_STATISTICS structure records statistical counters for the 802.11 interface.


## -syntax


````
typedef struct DOT11_STATISTICS {
  NDIS_OBJECT_HEADER         Header;
  ULONGLONG                  ullFourWayHandshakeFailures;
  ULONGLONG                  ullTKIPCounterMeasuresInvoked;
  ULONGLONG                  ullReserved;
  DOT11_MAC_FRAME_STATISTICS MacUcastCounters;
  DOT11_MAC_FRAME_STATISTICS MacMcastCounters;
  DOT11_PHY_FRAME_STATISTICS PhyCounters[1];
} DOT11_STATISTICS, *PDOT11_STATISTICS;
````


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_STATISTICS structure. This member is formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:



For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.


#### Revision

This member must be set to DOT11_STATISTICS_REVISION_1.


#### Size

This member must be set to 
       sizeof(DOT11_STATISTICS).


### -field ullFourWayHandshakeFailures

The number of four-way handshake failures that the 802.11 station encountered during Wi-Fi
     Protected Access (WPA) or Robust Security Network Association (RSNA) authentication.
     

If the 802.11 station is not performing the WPA or RSNA authentication, it should set this member to
     DOT11_STATISTICS_UNKNOWN.


### -field ullTKIPCounterMeasuresInvoked

The number of times that the 802.11 station invoked countermeasures following a message integrity
     code (MIC) failure.
     

If the 802.11 station is not performing TKIP countermeasures, it should set this member to
     DOT11_STATISTICS_UNKNOWN.


### -field ullReserved

This member is reserved for use by the operating system. The miniport driver must not write to
     this member.


### -field MacUcastCounters

The MAC layer counters based on unicast packets sent or received by the 802.11 station. The data
     structure for this member is the 
     <mshelp:link keywords="netvista.dot11_mac_frame_statistics" tabindex="0"><b>
     DOT11_MAC_FRAME_STATISTICS</b></mshelp:link> structure.
     
<div class="alert"><b>Note</b>  <p class="note"> Counters for received unicast packets must only be incremented for those packets with a
     destination MAC address in the 802.11 MAC header that matches the 802.11 station's MAC
     address.

</div><div> </div>

### -field MacMcastCounters

The MAC layer counters based on multicast or broadcast packets sent or received by the 802.11
     station. The data structure for this member is the 
     <mshelp:link keywords="netvista.dot11_mac_frame_statistics" tabindex="0"><b>
     DOT11_MAC_FRAME_STATISTICS</b></mshelp:link> structure.
     
<div class="alert"><b>Note</b>  <p class="note"> Counters for received multicast or broadcast packets must only be incremented for those
     packets with a destination MAC address in the 802.11 MAC header that matches an entry in the multicast
     address list of the 802.11 station. For more information about the multicast address list, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569388">OID_DOT11_MULTICAST_LIST</a>.

</div><div> </div>

### -field PhyCounters

An array of PHY layer counters. Each entry in this array is formatted as a 
     <mshelp:link keywords="netvista.dot11_phy_frame_statistics" tabindex="0"><b>
     DOT11_PHY_FRAME_STATISTICS</b></mshelp:link> structure.
     

The miniport driver must maintain an entry within the 
     <b>PhyCounters</b> array for each supported PHY. If the 802.11 station supports multiple PHYs of the same
     type, the miniport driver must create separate entries for each.

Entries within the 
     <b>PhyCounters</b> array must be in the same order as the list of supported PHYs that the driver returns
     when queried by 
     <mshelp:link keywords="netvista.oid_dot11_supported_phy_types" tabindex="0">
     OID_DOT11_SUPPORTED_PHY_TYPES</mshelp:link>.


## -remarks


The miniport driver must unconditionally set all of the counters in the DOT11_STATISTICS structure to
    zero, including MAC-layer and PHY-layer counters, when one of the following occurs:
<ul>
<li>
The driver's 
      <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function is
      called.

</li>
<li>
The driver's 
      <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function is
      called with an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a>,
      regardless of the type of reset operation specified in the set request.

</li>
</ul>For more information about the statistics gathered by a Native 802.11 miniport driver, see 
    <a href="https://msdn.microsoft.com/e6bd2abf-faa2-463f-91df-a15924afae96">Native 802.11 Statistics</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569420">OID_DOT11_STATISTICS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_STATISTICS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

