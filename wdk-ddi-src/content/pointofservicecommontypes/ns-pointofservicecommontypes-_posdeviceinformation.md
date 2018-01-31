---
UID: NS:pointofservicecommontypes._PosDeviceInformation
title: "_PosDeviceInformation"
author: windows-driver-content
description: This structure provides device information as defined in and required by the Unified Point of Service (UPOS) standard.
old-location: pos\posdeviceinformation.htm
old-project: pos
ms.assetid: 9ae1cfd1-1ef8-4f27-b6e1-f593bdc020e8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: pos.posdeviceinformation, PosDeviceInformation structure, _PosDeviceInformation, PosDeviceInformation, pointofservicecommontypes/PosDeviceInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	PointOfServiceCommonTypes.h
apiname:
-	PosDeviceInformation
product: Windows
targetos: Windows
req.typenames: PosDeviceInformation
---

# _PosDeviceInformation structure


## -description


This structure provides device information as defined in and required by the Unified Point of Service (UPOS) standard.


## -syntax


````
typedef struct _PosDeviceInformation {
  wchar_t UnifiedPOSVersion[STATISTICS_STRING_SIZE];
  wchar_t DeviceCategory[STATISTICS_STRING_SIZE];
  wchar_t ManufacturerName[STATISTICS_STRING_SIZE];
  wchar_t ModelName[STATISTICS_STRING_SIZE];
  wchar_t SerialNumber[STATISTICS_STRING_SIZE];
  wchar_t ManufactureDate[STATISTICS_STRING_SIZE];
  wchar_t MechanicalRevision[STATISTICS_STRING_SIZE];
  wchar_t FirmwareRevision[STATISTICS_STRING_SIZE];
  wchar_t Interface[STATISTICS_STRING_SIZE];
  wchar_t InstallationDate[STATISTICS_STRING_SIZE];
} PosDeviceInformation;
````


## -struct-fields




#### - UnifiedPOSVersion

Indicates the version of the UPOS specification supported.


#### - DeviceCategory

Indicates the device category (for example, POSPrinter or CashDrawer).


#### - ManufacturerName

Indicates the name of the device manufacturer.


#### - ModelName

Indicates the model name of the device.


#### - SerialNumber

Indicates the serial number of the device.


#### - ManufactureDate

Indicates the date the device was manufactured.


#### - MechanicalRevision

Indicates the device hardware revision.


#### - FirmwareRevision

Indicates the device firmware revision.


#### - Interface

Indicates the device hardware interface (for example, serial or USB).


#### - InstallationDate

Indicates the device installation date.


## -remarks


These strings must be NULL terminated, and the maximum length of the strings is <code>STATISTICS_STRING_SIZE - 1</code>.


