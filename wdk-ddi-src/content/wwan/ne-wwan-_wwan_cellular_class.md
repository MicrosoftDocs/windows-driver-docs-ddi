---
UID: NE:wwan._WWAN_CELLULAR_CLASS
title: _WWAN_CELLULAR_CLASS (wwan.h)
description: The WWAN_CELLULAR_CLASS enumeration lists the different classes of cellular technology that are supported by the MB device.
old-location: netvista\wwan_cellular_class.htm
tech.root: netvista
ms.assetid: c49f40b8-feb4-4dfd-9a2b-c800f3b5343a
ms.date: 05/02/2018
keywords: ["WWAN_CELLULAR_CLASS enumeration"]
ms.keywords: "*PWWAN_CELLULAR_CLASS, PWWAN_CELLULAR_CLASS, PWWAN_CELLULAR_CLASS enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_CELLULAR_CLASS, WWAN_CELLULAR_CLASS enumeration [Network Drivers Starting with Windows Vista], WwanCellularClassCdma, WwanCellularClassGsm, WwanCellularClassMax, WwanCellularClassUnknown, WwanRef_cbffbef4-6a05-4042-abf0-7495fadf869d.xml, _WWAN_CELLULAR_CLASS, netvista.wwan_cellular_class, wwan/PWWAN_CELLULAR_CLASS, wwan/WWAN_CELLULAR_CLASS, wwan/WwanCellularClassCdma, wwan/WwanCellularClassGsm, wwan/WwanCellularClassMax, wwan/WwanCellularClassUnknown"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.typenames: WWAN_CELLULAR_CLASS, *PWWAN_CELLULAR_CLASS
f1_keywords:
 - _WWAN_CELLULAR_CLASS
 - wwan/_WWAN_CELLULAR_CLASS
 - PWWAN_CELLULAR_CLASS
 - wwan/PWWAN_CELLULAR_CLASS
 - WWAN_CELLULAR_CLASS
 - wwan/WWAN_CELLULAR_CLASS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_CELLULAR_CLASS
---

# _WWAN_CELLULAR_CLASS enumeration


## -description

The WWAN_CELLULAR_CLASS enumeration lists the different classes of cellular technology that are
  supported by the MB device.

## -enum-fields

### -field WwanCellularClassUnknown

The device uses an unknown cellular technology.

### -field WwanCellularClassGsm

The device uses GSM-based technology.

### -field WwanCellularClassCdma

The device uses CDMA-based technology.

### -field WwanCellularClassMax

The total number of supported cellular classes.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a>