---
UID: NE:pointofservicecommontypes.DriverUnifiedPosErrorReason
title: DriverUnifiedPosErrorReason
author: windows-driver-content
description: This enumeration indicates the reason for the error.
old-location: pos\unifiedposerrorreason.htm
old-project: pos
ms.assetid: 2bbf5fcf-666e-4265-95cf-7e04670d59da
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NoService, Disabled, DriverUnifiedPosErrorReason enumeration, Failure, Extended, pointofservicecommontypes/Extended, Closed, pointofservicecommontypes/UnknownErrorReason, pointofservicecommontypes/Illegal, pointofservicecommontypes/Busy, Offline, pointofservicecommontypes/DriverUnifiedPosErrorReason, pointofservicecommontypes/Failure, pointofservicecommontypes/Closed, Illegal, Busy, pointofservicecommontypes/NoService, UnknownErrorReason, pointofservicecommontypes/Offline, Timeout, pointofservicecommontypes/ NoHardware, pos.unifiedposerrorreason, pointofservicecommontypes/Disabled, NoHardware, pointofservicecommontypes/Timeout, DriverUnifiedPosErrorReason
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




#### - UnknownErrorReason

The reason for the error is not known.


#### - NoService

Cannot communicate with the device due to the current configuration.


#### - Disabled

The device must be enabled in order to perform the operation.


#### - Illegal

The function is not available or is not supported on this device.


#### - NoHardware

The physical device is not connected or not powered on.


#### - Closed

The device is closed.


#### - Offline

The device is offline.


#### - Failure

The device is connected and powered on, but it failed to perform the operation.


#### - Timeout

The operation timed out on the device.


#### - Busy

The device is busy and cannot complete the operation.


#### - Extended

The device returned a vendor specified error.

