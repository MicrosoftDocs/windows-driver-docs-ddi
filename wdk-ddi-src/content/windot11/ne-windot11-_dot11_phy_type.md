---
UID: NE:windot11._DOT11_PHY_TYPE
title: _DOT11_PHY_TYPE (windot11.h)
description: The DOT11_PHY_TYPE enumeration is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_phy_type.htm
tech.root: netvista
ms.date: 03/17/2023
keywords: ["DOT11_PHY_TYPE enumeration"]
ms.keywords: "*PDOT11_PHY_TYPE, DOT11_PHY_TYPE, DOT11_PHY_TYPE enumeration [Network Drivers Starting with Windows Vista], Native_802.11_data_types_814496a3-4f7e-44a0-925c-0dbf64eb3f72.xml, PDOT11_PHY_TYPE, PDOT11_PHY_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _DOT11_PHY_TYPE, dot11_phy_type_IHV_end, dot11_phy_type_IHV_start, dot11_phy_type_any, dot11_phy_type_dsss, dot11_phy_type_erp, dot11_phy_type_fhss, dot11_phy_type_hrdsss, dot11_phy_type_ht, dot11_phy_type_irbaseband, dot11_phy_type_ofdm, dot11_phy_type_unknown, dot11_phy_type_vht, netvista.dot11_phy_type, windot11/DOT11_PHY_TYPE, windot11/PDOT11_PHY_TYPE, windot11/dot11_phy_type_IHV_end, windot11/dot11_phy_type_IHV_start, windot11/dot11_phy_type_any, windot11/dot11_phy_type_dsss, windot11/dot11_phy_type_erp, windot11/dot11_phy_type_fhss, windot11/dot11_phy_type_hrdsss, windot11/dot11_phy_type_ht, windot11/dot11_phy_type_irbaseband, windot11/dot11_phy_type_ofdm, windot11/dot11_phy_type_unknown, windot11/dot11_phy_type_vht"
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
req.typenames: DOT11_PHY_TYPE, *PDOT11_PHY_TYPE, DOT11_PHY_TYPE, *PDOT11_PHY_TYPE
f1_keywords:
 - _DOT11_PHY_TYPE
 - windot11/_DOT11_PHY_TYPE
 - PDOT11_PHY_TYPE
 - windot11/PDOT11_PHY_TYPE
 - DOT11_PHY_TYPE
 - windot11/DOT11_PHY_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - _DOT11_PHY_TYPE
 - PDOT11_PHY_TYPE
 - DOT11_PHY_TYPE
---

# _DOT11_PHY_TYPE enumeration


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_PHY_TYPE enumeration defines an 802.11 PHY and media type.

## -enum-fields

### -field dot11_phy_type_unknown:0

Specifies an unknown or uninitialized PHY type.

### -field dot11_phy_type_any:dot11_phy_type_unknown

Specifies an unknown or uninitialized PHY type.

### -field dot11_phy_type_fhss:1

Specifies a frequency-hopping spread-spectrum (FHSS) PHY.

### -field dot11_phy_type_dsss:2

Specifies a direct sequence spread spectrum (DSSS) PHY.

### -field dot11_phy_type_irbaseband:3

Specifies an infrared (IR) baseband PHY.

### -field dot11_phy_type_ofdm:4

Specifies an orthogonal frequency division multiplexing (OFDM) 802.11a PHY.

### -field dot11_phy_type_hrdsss:5

Specifies a high-rate DSSS (HRDSSS) 802.11b PHY.

### -field dot11_phy_type_erp:6

Specifies an extended-rate 802.11g PHY (ERP).

### -field dot11_phy_type_ht:7

Specifies a high-throughput (HT) 802.11n PHY. Each 802.11n PHY, whether dual-band or not, is
     specified as this PHY type.

### -field dot11_phy_type_vht:8

Specifies a very high-throughput (VHT) 802.11ac PHY.

### -field dot11_phy_type_dmg:9

Specifies a Directional Multi-Gigabit (DMG) 802.11ad PHY.

### -field dot11_phy_type_he:10

Specifies a High Efficiency (HE) 802.11ax PHY.

### -field dot11_phy_type_eht:11

Specifies an extremely high-throughput (EHT) 802.11be PHY.

### -field dot11_phy_type_IHV_start:0x80000000

Specifies the start of the range that is used to define proprietary PHY types that are developed
     by an independent hardware vendor (IHV).


The **dot11\_phy\_type\_IHV\_start** enumerator value is valid only when the miniport driver is operating in Extensible Station (ExtSTA) mode.

### -field dot11_phy_type_IHV_end:0xffffffff

Specifies the end of the range that is used to define proprietary PHY types that are developed by
     an IHV.


The **dot11\_phy\_type\_IHV\_end** enumerator value is valid only when the miniport driver is operating in ExtSTA mode.

## -remarks

An IHV can assign a value for its proprietary PHY types from **dot11\_phy\_type\_IHV\_start** through **dot11\_phy\_type\_IHV\_end**. The IHV must assign a unique number from this range for each of its proprietary PHY types.

## -see-also

[OID\_DOT11\_RECV\_SENSITIVITY\_LIST](/windows-hardware/drivers/network/oid-dot11-recv-sensitivity-list)

[OID\_DOT11\_SUPPORTED\_PHY\_TYPES](/windows-hardware/drivers/network/oid-dot11-supported-phy-types)

[ DOT11\_ASSOCIATION\_COMPLETION\_PARAMETERS](..\windot11\ns-windot11-dot11_association_completion_parameters.md)

[OID\_DOT11\_SCAN\_REQUEST](/windows-hardware/drivers/network/oid-dot11-scan-request)

