---
UID: NS:windot11.DOT11_VWIFI_ATTRIBUTES
title: DOT11_VWIFI_ATTRIBUTES
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_vwifi_attributes.htm
old-project: netvista
ms.assetid: 46eee6ea-8259-4036-b1c4-f0eef6587879
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11_VWIFI_ATTRIBUTES, netvista.dot11_vwifi_attributes, windot11/PDOT11_VWIFI_ATTRIBUTES, Native_802.11_data_types_fdecf787-d328-4546-a4fc-ac7205851ebf.xml, PDOT11_VWIFI_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], DOT11_VWIFI_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PDOT11_VWIFI_ATTRIBUTES, windot11/DOT11_VWIFI_ATTRIBUTES, *PDOT11_VWIFI_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   system.
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
-	DOT11_VWIFI_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: DOT11_VWIFI_ATTRIBUTES, *PDOT11_VWIFI_ATTRIBUTES
req.product: Windows 10 or later.
---

# DOT11_VWIFI_ATTRIBUTES structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_VWIFI_ATTRIBUTES structure defines the virtualization attributes of the miniport driver and
  802.11 station when operating in Virtual WiFi mode.


## -syntax


````
typedef struct DOT11_VWIFI_ATTRIBUTES {
  NDIS_OBJECT_HEADER      Header;
  ULONG                   uTotalNumOfEntries;
  DOT11_VWIFI_COMBINATION Combinations[1];
} DOT11_VWIFI_ATTRIBUTES, *PDOT11_VWIFI_ATTRIBUTES;
````


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_VWIFI_ATTRIBUTES structure. This member is formatted as
     an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_VWIFI_ATTRIBUTES_REVISION_1.



#### Size

This member must be set to 
       sizeof(DOT11_VWIFI_ATTRIBUTES).

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uTotalNumOfEntries

The maximum number of entries that the 
     <b>Combinations</b> array can contain.


### -field Combinations

The list of supported combinations of 802.11 MAC entities that an 802.11 miniport driver can
     simultaneously support when it is virtualized. Each entry in this list is specified through an array of 
     <a href="..\windot11\ns-windot11-_dot11_vwifi_combination.md">DOT11_VWIFI_COMBINATION</a>,  <a href="..\windot11\ns-windot11-_dot11_vwifi_combination_v2.md">
     DOT11_VWIFI_COMBINATION_V2</a>, or <a href="..\windot11\ns-windot11-_dot11_vwifi_combination_v3.md">DOT11_VWIFI_COMBINATION_V3</a> structures.


## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\windot11\ns-windot11-_dot11_vwifi_combination_v2.md">DOT11_VWIFI_COMBINATION_V2</a>



<a href="..\windot11\ns-windot11-_dot11_vwifi_combination.md">DOT11_VWIFI_COMBINATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_VWIFI_ATTRIBUTES structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

