---
UID: NE:pointofservicecommontypes.DriverUnifiedPosErrorReason
title: DriverUnifiedPosErrorReason
author: windows-driver-content
description: This enumeration indicates the reason for the error.
old-location: pos\unifiedposerrorreason.htm
tech.root: pos
ms.assetid: 2bbf5fcf-666e-4265-95cf-7e04670d59da
ms.date: 02/23/2018
ms.keywords: Busy, Closed, Disabled, DriverUnifiedPosErrorReason, DriverUnifiedPosErrorReason enumeration, Extended, Failure, Illegal, NoHardware, NoService, Offline, Timeout, UnknownErrorReason, pointofservicecommontypes/ NoHardware, pointofservicecommontypes/Busy, pointofservicecommontypes/Closed, pointofservicecommontypes/Disabled, pointofservicecommontypes/DriverUnifiedPosErrorReason, pointofservicecommontypes/Extended, pointofservicecommontypes/Failure, pointofservicecommontypes/Illegal, pointofservicecommontypes/NoService, pointofservicecommontypes/Offline, pointofservicecommontypes/Timeout, pointofservicecommontypes/UnknownErrorReason, pos.unifiedposerrorreason
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
-	DriverUnifiedPosErrorReason
product:
- Windows
targetos: Windows
req.typenames: DriverUnifiedPosErrorReason
---

# DriverUnifiedPosErrorReason enumeration


## -description


This enumeration indicates the reason for the error.


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

