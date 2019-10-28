---
UID: NE:pointofservicecommontypes._BarcodeStatus
title: _BarcodeStatus (pointofservicecommontypes.h)
description: This enumeration indicates barcode scanner status values.
old-location: pos\barcodestatus.htm
tech.root: pos
ms.assetid: b89ee18b-229d-4ec7-8c69-1b75ad0f3448
ms.date: 02/23/2018
ms.keywords: BarcodeStatus, BarcodeStatus enumeration, BarcodeStatusUpdateType_Extended, BarcodeStatusUpdateType_Off, BarcodeStatusUpdateType_OffOrOffline, BarcodeStatusUpdateType_Offline, BarcodeStatusUpdateType_Online, _BarcodeStatus, pointofservicecommontypes/BarcodeStatus, pointofservicecommontypes/BarcodeStatusUpdateType_Extended, pointofservicecommontypes/BarcodeStatusUpdateType_Off, pointofservicecommontypes/BarcodeStatusUpdateType_OffOrOffline, pointofservicecommontypes/BarcodeStatusUpdateType_Offline, pointofservicecommontypes/BarcodeStatusUpdateType_Online, pos.barcodestatus
ms.topic: enum
f1_keywords:
 - "pointofservicecommontypes/BarcodeStatus"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pointofservicecommontypes.h
api_name:
- BarcodeStatus
product:
- Windows
targetos: Windows
req.typenames: BarcodeStatus
---

# _BarcodeStatus enumeration


## -description


This enumeration indicates barcode scanner status values.


## -enum-fields




### -field BarcodeStatusUpdateType_Online

The device is online. This is valid if <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicecommontypes/ne-pointofservicecommontypes-driverunifiedpospowerreportingtype">UnifiedPosPowerReportingType</a> is <b>Standard</b> or <b>Advanced</b>.


### -field BarcodeStatusUpdateType_Off

The device power is off or detached from the terminal. This is valid if <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicecommontypes/ne-pointofservicecommontypes-driverunifiedpospowerreportingtype">UnifiedPosPowerReportingType</a> is <b>Advanced</b>.


### -field BarcodeStatusUpdateType_Offline

The device power is on, but it is not ready or unable to respond to requests. This is valid if <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicecommontypes/ne-pointofservicecommontypes-driverunifiedpospowerreportingtype">UnifiedPosPowerReportingType</a> is <b>Advanced</b>.


### -field BarcodeStatusUpdateType_OffOrOffline

The device power is off or the device is offline. This is valid if <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicecommontypes/ne-pointofservicecommontypes-driverunifiedpospowerreportingtype">UnifiedPosPowerReportingType</a> is <b>Standard</b>.


### -field BarcodeStatusUpdateType_Extended

Vendor specific status information.

