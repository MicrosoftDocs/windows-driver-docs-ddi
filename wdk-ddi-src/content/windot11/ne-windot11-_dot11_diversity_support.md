---
UID: NE:windot11._DOT11_DIVERSITY_SUPPORT
title: "_DOT11_DIVERSITY_SUPPORT"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_diversity_support.htm
tech.root: netvista
ms.assetid: 64eeb1bf-c18a-4dfa-b6ea-438d9e10fe4a
ms.date: 2/16/2018
ms.keywords: "*PDOT11_DIVERSITY_SUPPORT, DOT11_DIVERSITY_SUPPORT, DOT11_DIVERSITY_SUPPORT enumeration [Network Drivers Starting with Windows Vista], Native_802.11_data_types_29b0e3d8-450c-4d41-817b-ba83cc912168.xml, PDOT11_DIVERSITY_SUPPORT, PDOT11_DIVERSITY_SUPPORT enumeration pointer [Network Drivers Starting with Windows Vista], _DOT11_DIVERSITY_SUPPORT, dot11_diversity_support_dynamic, dot11_diversity_support_fixedlist, dot11_diversity_support_notsupported, dot11_diversity_support_unknown, netvista.dot11_diversity_support, windot11/DOT11_DIVERSITY_SUPPORT, windot11/PDOT11_DIVERSITY_SUPPORT, windot11/dot11_diversity_support_dynamic, windot11/dot11_diversity_support_fixedlist, windot11/dot11_diversity_support_notsupported, windot11/dot11_diversity_support_unknown"
ms.topic: enum
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	windot11.h
api_name:
-	DOT11_DIVERSITY_SUPPORT
product:
- Windows
targetos: Windows
req.typenames: DOT11_DIVERSITY_SUPPORT, *PDOT11_DIVERSITY_SUPPORT
product:
- Windows 10 or later.
---

# _DOT11_DIVERSITY_SUPPORT enumeration


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div>

The DOT11_DIVERSITY_SUPPORT enumeration specifies the type of antenna diversity supported by a PHY on
  the 802.11 station.


## -syntax


```cpp
typedef enum _DOT11_DIVERSITY_SUPPORT {
  dot11_diversity_support_unknown       = 0,
  dot11_diversity_support_fixedlist     = 1,
  dot11_diversity_support_notsupported  = 2,
  dot11_diversity_support_dynamic       = 3
} DOT11_DIVERSITY_SUPPORT, *PDOT11_DIVERSITY_SUPPORT;
```


## -enum-fields




### -field dot11_diversity_support_unknown

An uninitialized or unknown diversity support type.


### -field dot11_diversity_support_fixedlist

The PHY supports antenna diversity that is performed over the fixed list of antennas defined in
     the
     <b>dot11DiversitySelectionRx</b> MIB object. For more information about this MIB object, see
     <a href="https://msdn.microsoft.com/library/ee483634.aspx">
     OID_DOT11_DIVERSITY_SELECTION_RX</a>.


### -field dot11_diversity_support_notsupported

The PHY does not support antenna diversity.


### -field dot11_diversity_support_dynamic

The PHY supports antenna diversity and the dynamic control of diversity. The PHY layer management
     entity (LME) can dynamically modify the list of antennas specified by the
     <b>dot11DiversitySelectionRx</b> MIB object


## -see-also

<a href="https://msdn.microsoft.com/library/ee483634.aspx">
   OID_DOT11_DIVERSITY_SELECTION_RX</a>



 

 


