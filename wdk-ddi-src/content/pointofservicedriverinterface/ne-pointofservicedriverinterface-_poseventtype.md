---
UID: NE:pointofservicedriverinterface._PosEventType
title: "_PosEventType"
author: windows-driver-content
description: This enumeration defines values used in the PosEventDataHeader structure to indicate the type of event that was raised.
old-location: pos\poseventtype.htm
old-project: pos
ms.assetid: 2ba0c81f-2eff-48bf-8c3e-9047a398f735
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AlarmTimeoutExpired, BarcodeScannerDataReceived, BarcodeScannerErrorOccurred, BarcodeScannerImagePreviewReceived, BarcodeScannerTriggerPressed, BarcodeScannerTriggerReleased, DrawerClosed, DrawerOpened, InvalidEvent, MagneticStripeReaderDataReceived, MagneticStripeReaderErrorOccurred, PointOfServicePrinterErrorOccurred, PosEventType, PosEventType enumeration, ReleaseDeviceRequested, StatusUpdated, _Max, _PosEventType, pointofservicedriverinterface/AlarmTimeoutExpired, pointofservicedriverinterface/BarcodeScannerDataReceived, pointofservicedriverinterface/BarcodeScannerErrorOccurred, pointofservicedriverinterface/BarcodeScannerImagePreviewReceived, pointofservicedriverinterface/BarcodeScannerTriggerPressed, pointofservicedriverinterface/BarcodeScannerTriggerReleased, pointofservicedriverinterface/DrawerClosed, pointofservicedriverinterface/DrawerOpened, pointofservicedriverinterface/InvalidEvent, pointofservicedriverinterface/MagneticStripeReaderDataReceived, pointofservicedriverinterface/MagneticStripeReaderErrorOccurred, pointofservicedriverinterface/PointOfServicePrinterErrorOccurred, pointofservicedriverinterface/PosEventType, pointofservicedriverinterface/ReleaseDeviceRequested, pointofservicedriverinterface/StatusUpdated, pointofservicedriverinterface/_Max, pos.poseventtype
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pointofservicedriverinterface.h
api_name:
-	PosEventType
product: Windows
targetos: Windows
req.typenames: PosEventType
---

# _PosEventType enumeration


## -description


This enumeration defines values used in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn772232">PosEventDataHeader</a> structure to indicate the type of event that was raised.


## -enum-fields




### -field InvalidEvent

The event code is not valid.


### -field _MinEventType


### -field ReleaseDeviceRequested

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn790033">ReleaseDeviceRequested</a> event.


### -field StatusUpdated

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn790040">StatusUpdated</a> event.


### -field BarcodeScannerTriggerPressed

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757468">BarcodeScannerTriggerPressed</a> event.


### -field BarcodeScannerTriggerReleased

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757469">BarcodeScannerTriggerReleased</a> event.


### -field BarcodeScannerDataReceived

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757463">BarcodeScannerDataReceived</a> event.


### -field BarcodeScannerErrorOccurred

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757464">BarcodeScannerErrorOccurred</a> event.


### -field BarcodeScannerImagePreviewReceived

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757466">BarcodeScannerImagePreviewReceived</a> event.


### -field MagneticStripeReaderDataReceived

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn772149">MagneticStripeReaderDataReceived</a> event.


### -field MagneticStripeReaderErrorOccurred

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn772151">MagneticStripeReaderErrorOccured</a> event.


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

