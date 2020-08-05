---
UID: NS:pointofservicecommontypes._PosDeviceInformation
title: _PosDeviceInformation (pointofservicecommontypes.h)
description: This structure provides device information as defined in and required by the Unified Point of Service (UPOS) standard.
old-location: pos\posdeviceinformation.htm
tech.root: pos
ms.assetid: 9ae1cfd1-1ef8-4f27-b6e1-f593bdc020e8
ms.date: 02/23/2018
keywords: ["PosDeviceInformation structure"]
ms.keywords: PosDeviceInformation, PosDeviceInformation structure, _PosDeviceInformation, pointofservicecommontypes/PosDeviceInformation, pos.posdeviceinformation
f1_keywords:
 - "pointofservicecommontypes/PosDeviceInformation"
 - "PosDeviceInformation"
req.header: pointofservicecommontypes.h
req.include-header: PointOfServiceCommonTypes.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- PointOfServiceCommonTypes.h
api_name:
- PosDeviceInformation
targetos: Windows
req.typenames: PosDeviceInformation
---

# _PosDeviceInformation structure


## -description


This structure provides device information as defined in and required by the Unified Point of Service (UPOS) standard.


## -struct-fields




### -field UnifiedPOSVersion

Indicates the version of the UPOS specification supported.


### -field DeviceCategory

Indicates the device category (for example, POSPrinter or CashDrawer).


### -field ManufacturerName

Indicates the name of the device manufacturer.


### -field ModelName

Indicates the model name of the device.


### -field SerialNumber

Indicates the serial number of the device.


### -field ManufactureDate

Indicates the date the device was manufactured.


### -field MechanicalRevision

Indicates the device hardware revision.


### -field FirmwareRevision

Indicates the device firmware revision.


### -field Interface

Indicates the device hardware interface (for example, serial or USB).


### -field InstallationDate

Indicates the device installation date.


## -remarks



These strings must be NULL terminated, and the maximum length of the strings is <code>STATISTICS_STRING_SIZE - 1</code>.



