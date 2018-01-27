---
UID: NS:windot11._DOT11_VWIFI_COMBINATION_V3
title: _DOT11_VWIFI_COMBINATION_V3
author: windows-driver-content
description: The DOT11_VWIFI_COMBINATION_V3 structure contains the combination of MAC entities that an 802.11 wireless miniport driver simultaneously supports when virtualized.
old-location: netvista\dot11_vwifi_combination_v3.htm
old-project: netvista
ms.assetid: 65A397AE-B835-4043-9A81-24055901310B
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PDOT11_VWIFI_COMBINATION_V3, windot11/PDOT11_VWIFI_COMBINATION_V3, *PDOT11_VWIFI_COMBINATION_V3, netvista.dot11_vwifi_combination_v3, windot11/DOT11_VWIFI_COMBINATION_V3, DOT11_VWIFI_COMBINATION_V3, PDOT11_VWIFI_COMBINATION_V3 structure pointer [Network Drivers Starting with Windows Vista], _DOT11_VWIFI_COMBINATION_V3, DOT11_VWIFI_COMBINATION_V3 structure [Network Drivers Starting with Windows Vista]
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
-	DOT11_VWIFI_COMBINATION_V3
product: Windows
targetos: Windows
req.typenames: *PDOT11_VWIFI_COMBINATION_V3, DOT11_VWIFI_COMBINATION_V3
req.product: Windows 10 or later.
---

# _DOT11_VWIFI_COMBINATION_V3 structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_VWIFI_COMBINATION_V3</b> structure contains the combination of MAC entities that an 802.11 wireless miniport driver simultaneously supports when virtualized. 


## -syntax


````
typedef struct _DOT11_VWIFI_COMBINATION_V3 {
  NDIS_OBJECT_HEADER Header;
  ULONG              uNumInfrastructure;
  ULONG              uNumAdhoc;
  ULONG              uNumSoftAP;
  ULONG              uNumVirtualStation;
  ULONG              uNumWFDGroup;
} DOT11_VWIFI_COMBINATION_V3, *PDOT11_VWIFI_COMBINATION_V3;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>DOT11_VWIFI_COMBINATION_V3</b> structure. The required settings for the members of <b>Header</b> are the following.
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
<td>DOT11_VWIFI_COMBINATION_REVISION_3</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_VWIFI_COMBINATION_REVISION_3</td>
</tr>
</table> 


### -field uNumInfrastructure

The number of 802.11 infrastructure stations supported.


### -field uNumAdhoc

The number of adhoc stations supported.


### -field uNumSoftAP

The number of soft access point stations supported.


### -field uNumVirtualStation

The number of virtual stations supported.


### -field uNumWFDGroup

The number of simultaneous operational Wi-Fi Direct (WFD) groups supported.


## -remarks


When <b>uNumWFDGroup</b> &gt; 0, the miniport driver is required to support one more 802.11 MAC entity in addition to the number in <b>uNumWFDGroup</b>. This additional entity is used for WFD device functionality and is the only entity configured as <b>DOT11_OPERATION_MODE_WFD_DEVICE</b>.


