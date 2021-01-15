---
UID: NS:windot11.DOT11_ERP_PHY_ATTRIBUTES
title: DOT11_ERP_PHY_ATTRIBUTES (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_erp_phy_attributes.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_ERP_PHY_ATTRIBUTES structure"]
ms.keywords: "*PDOT11_ERP_PHY_ATTRIBUTES, DOT11_ERP_PHY_ATTRIBUTES, DOT11_ERP_PHY_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_ca561d35-8793-4e0f-8c56-81bd58365f08.xml, PDOT11_ERP_PHY_ATTRIBUTES, PDOT11_ERP_PHY_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_erp_phy_attributes, windot11/DOT11_ERP_PHY_ATTRIBUTES, windot11/PDOT11_ERP_PHY_ATTRIBUTES"
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
targetos: Windows
req.typenames: DOT11_ERP_PHY_ATTRIBUTES, *PDOT11_ERP_PHY_ATTRIBUTES
f1_keywords:
 - DOT11_ERP_PHY_ATTRIBUTES
 - windot11/DOT11_ERP_PHY_ATTRIBUTES
 - PDOT11_ERP_PHY_ATTRIBUTES
 - windot11/PDOT11_ERP_PHY_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_ERP_PHY_ATTRIBUTES
 - PDOT11_ERP_PHY_ATTRIBUTES
product:
 - Windows 10 or later.
---

# DOT11_ERP_PHY_ATTRIBUTES structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_ERP_PHY_ATTRIBUTES structure defines the attributes specific to an extended-rate PHY (ERP)
  type.

## -struct-fields

### -field HRDSSSAttributes

Since the ERP PHY type is a superset of the high-rate direct-sequence spread spectrum (HRDSS) PHY
     type, the start of the DOT11_ERP_PHY_ATTRIBUTES structure is formatted as a
     <a href="..\windot11\ns-windot11-dot11_hrdsss_phy_attributes.md">
     DOT11_HRDSSS_PHY_ATTRIBUTES</a> structure in order to define the HRDSS-specific attributes of the
     PHY.

### -field bERPPBCCOptionImplemented

A Boolean value that, if set to <b>TRUE</b>, specifies that the PHY supports enabled packet binary
     convolutional code (PBCC) modulation.


For more information about PBCC modulation, refer to Clause 18.4.6.6 of the IEEE 802.11b-1999
     standard. For more information about the ERP-PBCC option, refer to Clause 19.6 of the IEEE 802.11g-2003
     standard.

### -field bDSSSOFDMOptionImplemented

A Boolean value that, if set to <b>TRUE</b>, specifies the PHY has enabled the use of the hybrid
     DSSS-OFDM modulation. If the 802.11 station supports this option, the PHY is capable of combining the
     direct-sequence spread spectrum (DSSS) preamble and header with the orthogonal frequency division
     multiplexing (OFDM) payload.


For more information about DSSS-OFDM modulation, refer to Clause 19.7 of the IEEE 802.11g-2003
     standard.

### -field bShortSlotTimeOptionImplemented

A Boolean value that, if set to <b>TRUE</b>, specifies the PHY supports the 802.11g short slot time
     option. For more information about the short slot time, refer to Clause 7.3.1.4 of the IEEE 802.11g-2003
     standard.

## -syntax

```cpp
typedef struct DOT11_ERP_PHY_ATTRIBUTES {
  DOT11_HRDSSS_PHY_ATTRIBUTES HRDSSSAttributes;
  BOOLEAN                     bERPPBCCOptionImplemented;
  BOOLEAN                     bDSSSOFDMOptionImplemented;
  BOOLEAN                     bShortSlotTimeOptionImplemented;
} DOT11_ERP_PHY_ATTRIBUTES, *PDOT11_ERP_PHY_ATTRIBUTES;
```

## -remarks

The miniport driver defines the attributes of a PHY on the 802.11 station through the
    <a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a> structure, and
    formats the
    <b>ERPAttributes</b> member as a DOT11_ERP_PHY_ATTRIBUTES structure. The driver must only do this if the
    PHY defined by the DOT11_PHY_ATTRIBUTES structure is an ERP PHY type.

## -see-also

<a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a>



<a href="..\windot11\ns-windot11-dot11_hrdsss_phy_attributes.md">DOT11_HRDSSS_PHY_ATTRIBUTES</a>

