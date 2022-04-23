---
UID: NE:pointofservicedriverinterface._PosEventType
title: PosEventType (pointofservicedriverinterface.h)
description: This enumeration defines values used in the PosEventDataHeader structure to indicate the type of event that was raised.
tech.root: pos
ms.date: 04/19/2022
keywords: ["PosEventType enumeration"]
ms.keywords: AlarmTimeoutExpired, BarcodeScannerDataReceived, BarcodeScannerErrorOccurred, BarcodeScannerImagePreviewReceived, BarcodeScannerTriggerPressed, BarcodeScannerTriggerReleased, DrawerClosed, DrawerOpened, InvalidEvent, MagneticStripeReaderDataReceived, MagneticStripeReaderErrorOccurred, PointOfServicePrinterErrorOccurred, PosEventType, PosEventType enumeration, ReleaseDeviceRequested, StatusUpdated, _Max, _PosEventType, pointofservicedriverinterface/AlarmTimeoutExpired, pointofservicedriverinterface/BarcodeScannerDataReceived, pointofservicedriverinterface/BarcodeScannerErrorOccurred, pointofservicedriverinterface/BarcodeScannerImagePreviewReceived, pointofservicedriverinterface/BarcodeScannerTriggerPressed, pointofservicedriverinterface/BarcodeScannerTriggerReleased, pointofservicedriverinterface/DrawerClosed, pointofservicedriverinterface/DrawerOpened, pointofservicedriverinterface/InvalidEvent, pointofservicedriverinterface/MagneticStripeReaderDataReceived, pointofservicedriverinterface/MagneticStripeReaderErrorOccurred, pointofservicedriverinterface/PointOfServicePrinterErrorOccurred, pointofservicedriverinterface/PosEventType, pointofservicedriverinterface/ReleaseDeviceRequested, pointofservicedriverinterface/StatusUpdated, pointofservicedriverinterface/_Max, pos.poseventtype
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
targetos: Windows
req.typenames: PosEventType
f1_keywords:
 - _PosEventType
 - pointofservicedriverinterface/_PosEventType
 - PosEventType
 - pointofservicedriverinterface/PosEventType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pointofservicedriverinterface.h
api_name:
 - _PosEventType
 - PosEventType
---

## -description

This enumeration defines values used in the [PosEventDataHeader](/previous-versions/windows/hardware/previsioning-framework/dn772232(v=vs.85)) structure to indicate the type of event that was raised.

## -enum-fields

### -field InvalidEvent

The event code is not valid.

### -field _MinEventType

Reserved for internal use.

### -field ReleaseDeviceRequested

Represents the [ReleaseDeviceRequested](/previous-versions/windows/hardware/previsioning-framework/dn790033(v=vs.85)) event.

### -field StatusUpdated

Represents the [StatusUpdated](/previous-versions/windows/hardware/previsioning-framework/dn790040(v=vs.85)) event.

### -field BarcodeScannerTriggerPressed

Represents the [BarcodeScannerTriggerPressed](/previous-versions/windows/hardware/previsioning-framework/dn757468(v=vs.85)) event.

### -field BarcodeScannerTriggerReleased

Represents the [BarcodeScannerTriggerReleased](/previous-versions/windows/hardware/previsioning-framework/dn757469(v=vs.85)) event.

### -field BarcodeScannerDataReceived

Represents the [BarcodeScannerDataReceived](/previous-versions/windows/hardware/previsioning-framework/dn757463(v=vs.85)) event.

### -field BarcodeScannerErrorOccurred

Represents the [BarcodeScannerErrorOccurred](/previous-versions/windows/hardware/previsioning-framework/dn757464(v=vs.85)) event.

### -field BarcodeScannerImagePreviewReceived

Represents the [BarcodeScannerImagePreviewReceived](/previous-versions/windows/hardware/previsioning-framework/dn757466(v=vs.85)) event.

### -field MagneticStripeReaderDataReceived

Represents the [MagneticStripeReaderDataReceived](/previous-versions/windows/hardware/previsioning-framework/dn772149(v=vs.85)) event.

### -field MagneticStripeReaderErrorOccurred

Represents the [MagneticStripeReaderErrorOccurred](/previous-versions/windows/hardware/previsioning-framework/dn772151(v=vs.85)) event.

### -field _Max

Reserved for internal use.
