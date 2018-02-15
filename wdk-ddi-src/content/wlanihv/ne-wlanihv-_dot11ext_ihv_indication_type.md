---
UID: NE:wlanihv._DOT11EXT_IHV_INDICATION_TYPE
title: "_DOT11EXT_IHV_INDICATION_TYPE"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_indication_type.htm
old-project: netvista
ms.assetid: c4cba30d-f0ba-424b-aa05-2717fa8fcc4e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11ext_ihv_indication_type, DOT11EXT_IHV_INDICATION_TYPE enumeration [Network Drivers Starting with Windows Vista], wlanihv/IndicationTypeNicSpecificNotification, PDOT11EXT_IHV_INDICATION_TYPE, DOT11EXT_IHV_INDICATION_TYPE, wlanihv/PDOT11EXT_IHV_INDICATION_TYPE, wlanihv/DOT11EXT_IHV_INDICATION_TYPE, IndicationTypePmkidCandidateList, wlanihv/IndicationTypePmkidCandidateList, wlanihv/IndicationTypeTkipMicFailure, Native_802.11_data_types_57d8dd95-82d4-41e6-8ba3-b1ec5254b4b8.xml, IndicationTypePhyStateChange, *PDOT11EXT_IHV_INDICATION_TYPE, IndicationTypeTkipMicFailure, wlanihv/IndicationTypeLinkQuality, IndicationTypeLinkQuality, wlanihv/IndicationTypePhyStateChange, IndicationTypeNicSpecificNotification, _DOT11EXT_IHV_INDICATION_TYPE, PDOT11EXT_IHV_INDICATION_TYPE enumeration pointer [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wlanihv.h
req.include-header: Wlanihv.h
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
-	wlanihv.h
apiname:
-	DOT11EXT_IHV_INDICATION_TYPE
product: Windows
targetos: Windows
req.typenames: "*PDOT11EXT_IHV_INDICATION_TYPE, DOT11EXT_IHV_INDICATION_TYPE"
req.product: Windows 10 or later.
---

# _DOT11EXT_IHV_INDICATION_TYPE enumeration


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_INDICATION_TYPE enumeration specifies the indication types that can be sent by an
  IHV framework to an IHV module.


## -syntax


````
typedef enum _DOT11EXT_IHV_INDICATION_TYPE { 
  IndicationTypeNicSpecificNotification  = 0,
  IndicationTypePmkidCandidateList       = 1,
  IndicationTypeTkipMicFailure           = 2,
  IndicationTypePhyStateChange           = 3,
  IndicationTypeLinkQuality              = 4
} DOT11EXT_IHV_INDICATION_TYPE, *PDOT11EXT_IHV_INDICATION_TYPE;
````


## -enum-fields




### -field IndicationTypeNicSpecificNotification

Indicates a NIC-specific notification.


### -field IndicationTypePmkidCandidateList

Indicates a PMKID candidate list.


### -field IndicationTypeTkipMicFailure

Indicates a TKIP MIC failure.


### -field IndicationTypePhyStateChange

Indicates a PHY state change.


### -field IndicationTypeLinkQuality

Indicates link quality.

