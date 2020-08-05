---
UID: NE:pointofservicedriverinterface._PosEventType
title: _PosEventType (pointofservicedriverinterface.h)
description: This enumeration defines values used in the PosEventDataHeader structure to indicate the type of event that was raised.
old-location: pos\poseventtype.htm
tech.root: pos
ms.assetid: 2ba0c81f-2eff-48bf-8c3e-9047a398f735
ms.date: 02/23/2018
keywords: ["PosEventType enumeration"]
ms.keywords: AlarmTimeoutExpired, BarcodeScannerDataReceived, BarcodeScannerErrorOccurred, BarcodeScannerImagePreviewReceived, BarcodeScannerTriggerPressed, BarcodeScannerTriggerReleased, DrawerClosed, DrawerOpened, InvalidEvent, MagneticStripeReaderDataReceived, MagneticStripeReaderErrorOccurred, PointOfServicePrinterErrorOccurred, PosEventType, PosEventType enumeration, ReleaseDeviceRequested, StatusUpdated, _Max, _PosEventType, pointofservicedriverinterface/AlarmTimeoutExpired, pointofservicedriverinterface/BarcodeScannerDataReceived, pointofservicedriverinterface/BarcodeScannerErrorOccurred, pointofservicedriverinterface/BarcodeScannerImagePreviewReceived, pointofservicedriverinterface/BarcodeScannerTriggerPressed, pointofservicedriverinterface/BarcodeScannerTriggerReleased, pointofservicedriverinterface/DrawerClosed, pointofservicedriverinterface/DrawerOpened, pointofservicedriverinterface/InvalidEvent, pointofservicedriverinterface/MagneticStripeReaderDataReceived, pointofservicedriverinterface/MagneticStripeReaderErrorOccurred, pointofservicedriverinterface/PointOfServicePrinterErrorOccurred, pointofservicedriverinterface/PosEventType, pointofservicedriverinterface/ReleaseDeviceRequested, pointofservicedriverinterface/StatusUpdated, pointofservicedriverinterface/_Max, pos.poseventtype
f1_keywords:
 - "pointofservicedriverinterface/PosEventType"
 - "PosEventType"
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
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
- pointofservicedriverinterface.h
api_name:
- PosEventType
targetos: Windows
req.typenames: PosEventType
---

# _PosEventType enumeration


## -description


This enumeration defines values used in the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn772232(v=vs.85)">PosEventDataHeader</a> structure to indicate the type of event that was raised.


## -enum-fields




### -field InvalidEvent

The event code is not valid.


### -field _MinEventType


### -field ReleaseDeviceRequested

Represents the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn790033(v=vs.85)">ReleaseDeviceRequested</a> event.


### -field StatusUpdated

Represents the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn790040(v=vs.85)">StatusUpdated</a> event.


### -field BarcodeScannerTriggerPressed

Represents the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn757468(v=vs.85)">BarcodeScannerTriggerPressed</a> event.


### -field BarcodeScannerTriggerReleased

Represents the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn757469(v=vs.85)">BarcodeScannerTriggerReleased</a> event.


### -field BarcodeScannerDataReceived

Represents the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn757463(v=vs.85)">BarcodeScannerDataReceived</a> event.


### -field BarcodeScannerErrorOccurred

Represents the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn757464(v=vs.85)">BarcodeScannerErrorOccurred</a> event.


### -field BarcodeScannerImagePreviewReceived

Represents the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn757466(v=vs.85)">BarcodeScannerImagePreviewReceived</a> event.


### -field MagneticStripeReaderDataReceived

Represents the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn772149(v=vs.85)">MagneticStripeReaderDataReceived</a> event.


### -field MagneticStripeReaderErrorOccurred

Represents the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn772151(v=vs.85)">MagneticStripeReaderErrorOccured</a> event.


### -field PointOfServicePrinterErrorOccurred

Represents the PointOfServicePrinterErrorOccurred event.


### -field AlarmTimeoutExpired

Represents the AlarmTimeoutExpired event.


### -field DrawerClosed

Represents the DrawerClosed event.


### -field DrawerOpened

Represents the DrawerOpened event.


### -field _Max

Represents the _Max event.

