---
UID: NE:wditypes._WDI_PHY_TYPE
title: "_WDI_PHY_TYPE"
author: windows-driver-content
description: The WDI_PHY_TYPE enumeration defines the PHY types.
old-location: netvista\wdi_phy_type.htm
tech.root: netvista
ms.assetid: BDA90056-6DAA-4FC8-82EC-3062087E02C4
ms.date: 05/02/2018
ms.keywords: WDI_PHY_TYPE, WDI_PHY_TYPE enumeration [Network Drivers Starting with Windows Vista], WDI_PHY_TYPE_ANY, WDI_PHY_TYPE_DMG, WDI_PHY_TYPE_DSSS, WDI_PHY_TYPE_ERP, WDI_PHY_TYPE_FHSS, WDI_PHY_TYPE_HRDSSS, WDI_PHY_TYPE_HT, WDI_PHY_TYPE_IHV_END, WDI_PHY_TYPE_IHV_START, WDI_PHY_TYPE_IRBASEBAND, WDI_PHY_TYPE_OFDM, WDI_PHY_TYPE_UNKNOWN, WDI_PHY_TYPE_VHT, _WDI_PHY_TYPE, netvista.wdi_phy_type, netvista.wifi_phy_type, wditypes/WDI_PHY_TYPE, wditypes/WDI_PHY_TYPE_ANY, wditypes/WDI_PHY_TYPE_DMG, wditypes/WDI_PHY_TYPE_DSSS, wditypes/WDI_PHY_TYPE_ERP, wditypes/WDI_PHY_TYPE_FHSS, wditypes/WDI_PHY_TYPE_HRDSSS, wditypes/WDI_PHY_TYPE_HT, wditypes/WDI_PHY_TYPE_IHV_END, wditypes/WDI_PHY_TYPE_IHV_START, wditypes/WDI_PHY_TYPE_IRBASEBAND, wditypes/WDI_PHY_TYPE_OFDM, wditypes/WDI_PHY_TYPE_UNKNOWN, wditypes/WDI_PHY_TYPE_VHT
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	wditypes.hpp
api_name:
-	WDI_PHY_TYPE
product:
- Windows
targetos: Windows
req.typenames: WDI_PHY_TYPE
---

# _WDI_PHY_TYPE enumeration


## -description


The WDI_PHY_TYPE enumeration defines the PHY types.


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
