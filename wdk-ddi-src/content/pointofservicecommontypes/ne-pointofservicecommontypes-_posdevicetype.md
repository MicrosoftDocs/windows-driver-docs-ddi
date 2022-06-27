---
UID: NE:pointofservicecommontypes._PosDeviceType
title: _PosDeviceType (pointofservicecommontypes.h)
description: This enumeration defines values used in the PosDeviceBasicsType structure to indicate the type of device (for instance, barcode scanner or magnetic stripe reader).
tech.root: pos
ms.date: 04/18/2022
keywords: ["PosDeviceType enumeration"]
ms.keywords: PosDeviceType, PosDeviceType enumeration, PosDeviceType_BarcodeScanner, PosDeviceType_CashDrawer, PosDeviceType_MagneticStripeReader, PosDeviceType_Max, PosDeviceType_Printer, PosDeviceType_Unknown, _PosDeviceType, pointofservicecommontypes/PosDeviceType, pointofservicecommontypes/PosDeviceType_BarcodeScanner, pointofservicecommontypes/PosDeviceType_CashDrawer, pointofservicecommontypes/PosDeviceType_MagneticStripeReader, pointofservicecommontypes/PosDeviceType_Max, pointofservicecommontypes/PosDeviceType_Printer, pointofservicecommontypes/PosDeviceType_Unknown, pos.posdevicetype
req.header: pointofservicecommontypes.h
req.include-header: Pointofservicecommontypes.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: PosDeviceType
f1_keywords:
 - _PosDeviceType
 - pointofservicecommontypes/_PosDeviceType
 - PosDeviceType
 - pointofservicecommontypes/PosDeviceType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pointofservicecommontypes.h
api_name:
 - _PosDeviceType
 - PosDeviceType
---

## -description

This enumeration defines values used in the [PosDeviceBasicsType](../pointofservicedriverinterface/ns-pointofservicedriverinterface-_posdevicebasicstype.md) structure to indicate the type of device (for instance, barcode scanner or magnetic stripe reader).

## -enum-fields

### -field PosDeviceType_Unknown

Indicates that the type of device is not known.

### -field PosDeviceType_BarcodeScanner

Indicates that the type of device is a barcode scanner.

### -field PosDeviceType_MagneticStripeReader

Indicates that the type of device is a magnetic stripe reader.

### -field PosDeviceType_Max

Unused.