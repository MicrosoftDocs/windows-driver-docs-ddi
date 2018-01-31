---
UID: NE:pointofservicedriverinterface._PosEventType
title: "_PosEventType"
author: windows-driver-content
description: This enumeration defines values used in the PosEventDataHeader structure to indicate the type of event that was raised.
old-location: pos\poseventtype.htm
old-project: pos
ms.assetid: 2ba0c81f-2eff-48bf-8c3e-9047a398f735
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: BarcodeScannerErrorOccurred, BarcodeScannerTriggerPressed, pointofservicedriverinterface/BarcodeScannerDataReceived, pointofservicedriverinterface/BarcodeScannerTriggerPressed, BarcodeScannerImagePreviewReceived, pointofservicedriverinterface/StatusUpdated, MagneticStripeReaderErrorOccurred, AlarmTimeoutExpired, pointofservicedriverinterface/BarcodeScannerTriggerReleased, pointofservicedriverinterface/BarcodeScannerErrorOccurred, PosEventType, DrawerOpened, DrawerClosed, pointofservicedriverinterface/InvalidEvent, _PosEventType, _Max, pointofservicedriverinterface/DrawerClosed, PosEventType enumeration, ReleaseDeviceRequested, BarcodeScannerTriggerReleased, pointofservicedriverinterface/DrawerOpened, pointofservicedriverinterface/ReleaseDeviceRequested, InvalidEvent, MagneticStripeReaderDataReceived, pointofservicedriverinterface/AlarmTimeoutExpired, PointOfServicePrinterErrorOccurred, pointofservicedriverinterface/BarcodeScannerImagePreviewReceived, pointofservicedriverinterface/_Max, StatusUpdated, pointofservicedriverinterface/PointOfServicePrinterErrorOccurred, pointofservicedriverinterface/MagneticStripeReaderDataReceived, pos.poseventtype, BarcodeScannerDataReceived, pointofservicedriverinterface/MagneticStripeReaderErrorOccurred, pointofservicedriverinterface/PosEventType
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
req.lib: 
req.dll: 
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pointofservicedriverinterface.h
apiname:
-	PosEventType
product: Windows
targetos: Windows
req.typenames: PosEventType
---

# _PosEventType enumeration


## -description


This enumeration defines values used in the <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_poseventdataheader.md">PosEventDataHeader</a> structure to indicate the type of event that was raised.


## -syntax


````
typedef enum _PosEventType { 
  InvalidEvent                        = 0,
  ReleaseDeviceRequested              = 1,
  StatusUpdated                       = 2,
  BarcodeScannerTriggerPressed        = 3,
  BarcodeScannerTriggerReleased       = 4,
  BarcodeScannerDataReceived          = 5,
  BarcodeScannerErrorOccurred         = 6,
  BarcodeScannerImagePreviewReceived  = 7,
  MagneticStripeReaderDataReceived    = 8,
  MagneticStripeReaderErrorOccurred   = 9,
  PointOfServicePrinterErrorOccurred  = 10,
  AlarmTimeoutExpired                 = 11,
  DrawerClosed                        = 12,
  DrawerOpened                        = 13,
  _Max                                = 14
} PosEventType;
````


## -enum-fields




#### - InvalidEvent

The event code is not valid.


### -field _MinEventType



#### - ReleaseDeviceRequested

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn790033">ReleaseDeviceRequested</a> event.


#### - StatusUpdated

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn790040">StatusUpdated</a> event.


#### - BarcodeScannerTriggerPressed

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757468">BarcodeScannerTriggerPressed</a> event.


#### - BarcodeScannerTriggerReleased

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757469">BarcodeScannerTriggerReleased</a> event.


#### - BarcodeScannerDataReceived

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757463">BarcodeScannerDataReceived</a> event.


#### - BarcodeScannerErrorOccurred

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757464">BarcodeScannerErrorOccurred</a> event.


#### - BarcodeScannerImagePreviewReceived

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757466">BarcodeScannerImagePreviewReceived</a> event.


#### - MagneticStripeReaderDataReceived

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn772149">MagneticStripeReaderDataReceived</a> event.


#### - MagneticStripeReaderErrorOccurred

Represents the <a href="https://msdn.microsoft.com/library/windows/hardware/dn772151">MagneticStripeReaderErrorOccured</a> event.


#### - PointOfServicePrinterErrorOccurred

Represents the PointOfServicePrinterErrorOccurred event.


#### - AlarmTimeoutExpired

Represents the AlarmTimeoutExpired event.


#### - DrawerClosed

Represents the DrawerClosed event.


#### - DrawerOpened

Represents the DrawerOpened event.


#### - _Max

Represents the _Max event.

