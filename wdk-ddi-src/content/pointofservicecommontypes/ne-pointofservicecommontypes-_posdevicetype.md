---
UID: NE:pointofservicecommontypes._PosDeviceType
title: "_PosDeviceType"
author: windows-driver-content
description: This enumeration defines values used in the PosDeviceBasicsType structure to indicate the type of device (for instance, barcode scanner or magnetic stripe reader).
old-location: pos\posdevicetype.htm
old-project: pos
ms.assetid: 1e0b4b66-f9aa-4315-a07d-b6fd47f10371
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: pos.posdevicetype, PosDeviceType_CashDrawer, pointofservicecommontypes/PosDeviceType_Max, PosDeviceType_Max, PosDeviceType, pointofservicecommontypes/PosDeviceType_CashDrawer, PosDeviceType_MagneticStripeReader, PosDeviceType_Unknown, _PosDeviceType, PosDeviceType_Printer, pointofservicecommontypes/PosDeviceType_BarcodeScanner, pointofservicecommontypes/PosDeviceType, pointofservicecommontypes/PosDeviceType_Printer, pointofservicecommontypes/PosDeviceType_Unknown, pointofservicecommontypes/PosDeviceType_MagneticStripeReader, PosDeviceType enumeration, PosDeviceType_BarcodeScanner
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
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pointofservicecommontypes.h
apiname:
-	PosDeviceType
product: Windows
targetos: Windows
req.typenames: PosDeviceType
---

# _PosDeviceType enumeration


## -description


This enumeration defines values used in the <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posdevicebasicstype.md">PosDeviceBasicsType</a> structure to indicate the type of device (for instance, barcode scanner or magnetic stripe reader). 


## -syntax


````
typedef enum _PosDeviceType { 
  PosDeviceType_Unknown               = 0,
  PosDeviceType_BarcodeScanner        = 1,
  PosDeviceType_MagneticStripeReader  = 2,
  PosDeviceType_Printer               = 3,
  PosDeviceType_CashDrawer            = 4,
  PosDeviceType_Max                   = 5
} PosDeviceType;
````


## -enum-fields




#### - PosDeviceType_Unknown

Indicates that the type of device is not known.


#### - PosDeviceType_BarcodeScanner

Indicates that the type of device is a barcode scanner.


#### - PosDeviceType_MagneticStripeReader

Indicates that the type of device is a magnetic stripe reader.


#### - PosDeviceType_Printer

Indicates that the type of device is a printer.


#### - PosDeviceType_CashDrawer

Indicates that the type of device is a cash drawer.


### -field PosDeviceType_LineDisplay



#### - PosDeviceType_Max

Unused.

