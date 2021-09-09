---
UID: NE:dot11wificxtypes._WDI_PHY_TYPE
tech.root: netvista
<<<<<<< HEAD
title: WDI_PHY_TYPE (dot11wificxtypes.h)
ms.date: 06/17/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_PHY_TYPE enumeration defines PHY types.
=======
title: WDI_PHY_TYPE
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WDI_PHY_TYPE enumeration for internal use only. Don't use this enumeration in your code."
>>>>>>> main
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11Windows 11
>>>>>>> main
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_PHY_TYPE
 - WDI_PHY_TYPE
f1_keywords:
 - _WDI_PHY_TYPE
 - dot11wificxtypes/_WDI_PHY_TYPE
 - WDI_PHY_TYPE
 - dot11wificxtypes/WDI_PHY_TYPE
dev_langs:
 - c++
---

## -description

The **WDI_PHY_TYPE** enumeration defines the PHY types.

## -enum-fields

### -field WDI_PHY_TYPE_UNKNOWN

Specifies an unknown or uninitialized PHY type.

### -field WDI_PHY_TYPE_ANY

Specifies an unknown or uninitialized PHY type.

### -field WDI_PHY_TYPE_FHSS

Specifies a frequency-hopping spread-spectrum (FHSS) PHY.

### -field WDI_PHY_TYPE_DSSS

Specifies a direct sequence spread spectrum (DSSS) PHY.

### -field WDI_PHY_TYPE_IRBASEBAND

Specifies an infrared (IR) baseband PHY.

### -field WDI_PHY_TYPE_OFDM

Specifies an orthogonal frequency division multiplexing (OFDM) 802.11a PHY.

### -field WDI_PHY_TYPE_HRDSSS

Specifies a high-rate DSSS (HRDSSS) 802.11b PHY.

### -field WDI_PHY_TYPE_ERP

Specifies an extended-rate 802.11g PHY (ERP).

### -field WDI_PHY_TYPE_HT

Specifies a high-throughput (HT) 802.11n PHY. Each 802.11n PHY, whether dual-band or not, is specified as this PHY type.

### -field WDI_PHY_TYPE_VHT

Specifies a very high-throughput (VHT) 802.11ac PHY.

### -field WDI_PHY_TYPE_DMG

Added in Windows 10, version 1607, WDI version 1.0.21.

Specifies a Directional Multi-Gigabit (DMG) 802.11ad PHY.

### -field WDI_PHY_TYPE_HE

Added in Windows 10, version 1809. WDI version 1.1.7.

Specifies a High-Efficiency (HE) 802.11ax PHY.

### -field WDI_PHY_TYPE_IHV_START

Specifies the start of the range that is used to define proprietary PHY types that are developed by an independent hardware vendor (IHV).

### -field WDI_PHY_TYPE_IHV_END

Specifies the end of the range that is used to define proprietary PHY types that are developed by an IHV.

## -remarks

The **WDI_PHY_TYPE** enum is a value in the [**WDI_TLV_PHY_TYPE_LIST**](/windows-hardware/drivers/netcx/wdi-tlv-phy-type-list) and [**WDI_TLV_PHY_STATISTICS**](/windows-hardware/drivers/netcx/wdi-tlv-phy-statistics) TLVs.

## -see-also

[**WDI_TLV_PHY_TYPE_LIST**](/windows-hardware/drivers/netcx/wdi-tlv-phy-type-list) 

[**WDI_TLV_PHY_STATISTICS**](/windows-hardware/drivers/netcx/wdi-tlv-phy-statistics)