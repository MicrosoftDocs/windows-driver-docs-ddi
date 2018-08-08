---
UID: NE:pointofservicecommontypes._PosDeviceType
title: "_PosDeviceType"
author: windows-driver-content
description: This enumeration defines values used in the PosDeviceBasicsType structure to indicate the type of device (for instance, barcode scanner or magnetic stripe reader).
old-location: pos\posdevicetype.htm
tech.root: pos
ms.assetid: 1e0b4b66-f9aa-4315-a07d-b6fd47f10371
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PosDeviceType, PosDeviceType enumeration, PosDeviceType_BarcodeScanner, PosDeviceType_CashDrawer, PosDeviceType_MagneticStripeReader, PosDeviceType_Max, PosDeviceType_Printer, PosDeviceType_Unknown, _PosDeviceType, pointofservicecommontypes/PosDeviceType, pointofservicecommontypes/PosDeviceType_BarcodeScanner, pointofservicecommontypes/PosDeviceType_CashDrawer, pointofservicecommontypes/PosDeviceType_MagneticStripeReader, pointofservicecommontypes/PosDeviceType_Max, pointofservicecommontypes/PosDeviceType_Printer, pointofservicecommontypes/PosDeviceType_Unknown, pos.posdevicetype
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pointofservicecommontypes.h
api_name:
-	PosDeviceType
product:
- Windows
targetos: Windows
req.typenames: PosDeviceType
---

# _PosDeviceType enumeration


## -description


This enumeration defines values used in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn772213">PosDeviceBasicsType</a> structure to indicate the type of device (for instance, barcode scanner or magnetic stripe reader). 


## -enum-fields




### -field PosDeviceType_Unknown

Indicates that the type of device is not known.


### -field PosDeviceType_BarcodeScanner

Indicates that the type of device is a barcode scanner.


### -field PosDeviceType_MagneticStripeReader

Indicates that the type of device is a magnetic stripe reader.


### -field PosDeviceType_Printer

Indicates that the type of device is a printer.


### -field PosDeviceType_CashDrawer

Indicates that the type of device is a cash drawer.


### -field PosDeviceType_LineDisplay


### -field PosDeviceType_Max

Unused.

