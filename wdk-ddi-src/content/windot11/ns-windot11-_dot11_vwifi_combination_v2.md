---
UID: NS:windot11._DOT11_VWIFI_COMBINATION_V2
title: "_DOT11_VWIFI_COMBINATION_V2"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_vwifi_combination_v2.htm
old-project: netvista
ms.assetid: b30b868d-3012-4bdc-80f4-ffae2ebaa4d6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: windot11/PDOT11_VWIFI_COMBINATION_V2, DOT11_VWIFI_COMBINATION_V2 structure [Network Drivers Starting with Windows Vista], DOT11_VWIFI_COMBINATION_V2, netvista.dot11_vwifi_combination_v2, PDOT11_VWIFI_COMBINATION_V2 structure pointer [Network Drivers Starting with Windows Vista], *PDOT11_VWIFI_COMBINATION_V2, windot11/DOT11_VWIFI_COMBINATION_V2, PDOT11_VWIFI_COMBINATION_V2, _DOT11_VWIFI_COMBINATION_V2, Native_802.11_data_types_1210442c-19be-406c-bec5-12ad170fc90b.xml
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
-	DOT11_VWIFI_COMBINATION_V2
product: Windows
targetos: Windows
req.typenames: "*PDOT11_VWIFI_COMBINATION_V2, DOT11_VWIFI_COMBINATION_V2"
req.product: Windows 10 or later.
---

# _DOT11_VWIFI_COMBINATION_V2 structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_VWIFI_COMBINATION_V2 structure specifies the combination of 802.11 MAC entities that an
  802.11 miniport driver can simultaneously support when it is virtualized.


## -syntax


````
typedef struct _DOT11_VWIFI_COMBINATION_V2 {
  NDIS_OBJECT_HEADER Header;
  ULONG              uNumInfrastructure;
  ULONG              uNumAdhoc;
  ULONG              uNumSoftAP;
  ULONG              uNumVirtualStation;
} DOT11_VWIFI_COMBINATION_V2, *PDOT11_VWIFI_COMBINATION_V2;
````


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_VWIFI_COMBINATION_V2 structure. This member is formatted
     as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_VWIFI_COMBINATION_REVISION_2.



#### Size

This member must be set to 
       sizeof(DOT11_VWIFI_COMBINATION_V2).

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uNumInfrastructure

The number of 802.11 infrastructure stations supported. For more information, see the following
     Remarks section.


### -field uNumAdhoc

The number of Adhoc Stations supported. For more information, see the following Remarks
     section.


### -field uNumSoftAP

The number of Soft AP Stations supported. For more information, see the following Remarks
     section.


### -field uNumVirtualStation

The number of Virtual Stations supported. For more information, see the following Remarks
     section.


## -remarks



Starting with Windows 7, the 802.11 miniport driver must only report one or more of the following
    combinations of member values.

<b>No 802.11 Virtual Station
     </b>

<ul>
<li>
<b>uNumInfrastructure</b> = 1

</li>
<li>
<b>uNumAdhoc</b> = 0

</li>
<li>
<b>uNumSoftAP</b> = 1

</li>
<li>
<b>uNumVirtualStation</b> = 0

</li>
</ul>
<b>One 802.11 Virtual Station
     </b>

<ul>
<li>
<b>uNumInfrastructure</b> = 1

</li>
<li>
<b>uNumAdhoc</b> = 0

</li>
<li>
<b>uNumSoftAP</b> = 1

</li>
<li>
<b>uNumVirtualStation</b> = 1

</li>
</ul>



## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_VWIFI_COMBINATION_V2 structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

