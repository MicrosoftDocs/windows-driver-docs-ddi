---
UID: NE:pointofservicecommontypes.DriverUnifiedPosErrorReason
title: DriverUnifiedPosErrorReason
author: windows-driver-content
description: This enumeration indicates the reason for the error.
old-location: pos\unifiedposerrorreason.htm
old-project: pos
ms.assetid: 2bbf5fcf-666e-4265-95cf-7e04670d59da
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: Closed, pointofservicecommontypes/UnknownErrorReason, DriverUnifiedPosErrorReason enumeration, NoHardware, pointofservicecommontypes/Illegal, Illegal, NoService, pointofservicecommontypes/Busy, Failure, pointofservicecommontypes/Offline, DriverUnifiedPosErrorReason, Offline, Timeout, pos.unifiedposerrorreason, pointofservicecommontypes/Closed, pointofservicecommontypes/Disabled, UnknownErrorReason, pointofservicecommontypes/Failure, Extended, pointofservicecommontypes/ NoHardware, pointofservicecommontypes/DriverUnifiedPosErrorReason, pointofservicecommontypes/NoService, Disabled, pointofservicecommontypes/Timeout, pointofservicecommontypes/Extended, Busy
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
-	DriverUnifiedPosErrorReason
product: Windows
targetos: Windows
req.typenames: DriverUnifiedPosErrorReason
---

# DriverUnifiedPosErrorReason enumeration


## -description


This enumeration indicates the reason for the error.


## -syntax


````
typedef enum _DriverUnifiedPosErrorReason { 
  UnknownErrorReason  = 0,
  NoService           = 1,
  Disabled            = 2,
  Illegal             = 3,
   NoHardware         = 4,
  Closed              = 5,
  Offline             = 6,
  Failure             = 7,
  Timeout             = 8,
  Busy                = 9,
  Extended            = 10
} DriverUnifiedPosErrorReason;
````


## -enum-fields




### -field UnknownErrorReason

The reason for the error is not known.


### -field NoService

Cannot communicate with the device due to the current configuration.


### -field Disabled

The device must be enabled in order to perform the operation.


### -field Illegal

The function is not available or is not supported on this device.


### -field NoHardware

The physical device is not connected or not powered on.


### -field Closed

The device is closed.


### -field Offline

The device is offline.


### -field Failure

The device is connected and powered on, but it failed to perform the operation.


### -field Timeout

The operation timed out on the device.


### -field Busy

The device is busy and cannot complete the operation.


### -field Extended

The device returned a vendor specified error.

