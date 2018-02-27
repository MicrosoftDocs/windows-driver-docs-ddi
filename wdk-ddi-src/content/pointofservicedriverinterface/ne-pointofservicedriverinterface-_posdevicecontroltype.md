---
UID: NE:pointofservicedriverinterface._PosDeviceControlType
title: "_PosDeviceControlType"
author: windows-driver-content
description: This enumeration defines values for the IOCTLs of the scanner driver and magnetic stripe reader (MSR) driver.
old-location: pos\posdevicecontroltype.htm
old-project: pos
ms.assetid: 9f5f3baa-49a0-4711-88c0-b9ff8d87ae1d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: BarcodeScannerInjectEvent, CheckHealth, ClaimDevice, GetDeviceBasics, GetProperty, Invalid, MsrAuthenticateDevice, MsrDeAuthenticateDevice, MsrRetrieveDeviceAuthentication, MsrUpdateKey, PosDeviceControlType, PosDeviceControlType enumeration, ReleaseDevice, ResetStatistics, RetainDevice, RetrieveStatistics, SetProperty, UpdateStatistics, _MaxDeviceControlType, _PosDeviceControlType, pointofservicedriverinterface/BarcodeScannerInjectEvent, pointofservicedriverinterface/CheckHealth, pointofservicedriverinterface/ClaimDevice, pointofservicedriverinterface/GetDeviceBasics, pointofservicedriverinterface/GetProperty, pointofservicedriverinterface/Invalid, pointofservicedriverinterface/MsrAuthenticateDevice, pointofservicedriverinterface/MsrDeAuthenticateDevice, pointofservicedriverinterface/MsrRetrieveDeviceAuthentication, pointofservicedriverinterface/MsrUpdateKey, pointofservicedriverinterface/PosDeviceControlType, pointofservicedriverinterface/ReleaseDevice, pointofservicedriverinterface/ResetStatistics, pointofservicedriverinterface/RetainDevice, pointofservicedriverinterface/RetrieveStatistics, pointofservicedriverinterface/SetProperty, pointofservicedriverinterface/UpdateStatistics, pointofservicedriverinterface/_MaxDeviceControlType, pos.posdevicecontroltype
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
-	PosDeviceControlType
product: Windows
targetos: Windows
req.typenames: PosDeviceControlType
---

# _PosDeviceControlType enumeration


## -description


This enumeration defines values for the IOCTLs of the scanner driver and magnetic stripe reader (MSR) driver.


## -syntax


````
typedef enum _PosDeviceControlType { 
  Invalid                          = 0,
  GetProperty                      = 1,
  SetProperty                      = 2,
  ClaimDevice                      = 3,
  ReleaseDevice                    = 4,
  RetainDevice                     = 5,
  RetrieveStatistics               = 6,
  ResetStatistics                  = 7,
  UpdateStatistics                 = 8,
  CheckHealth                      = 9,
  GetDeviceBasics                  = 10,
  BarcodeScannerInjectEvent        = 11,
  MsrRetrieveDeviceAuthentication  = 12,
  MsrAuthenticateDevice            = 13,
  MsrDeAuthenticateDevice          = 14,
  MsrUpdateKey                     = 15,
  _MaxDeviceControlType            = 16
} PosDeviceControlType;
````


## -enum-fields




### -field _MinDeviceControlType


### -field Invalid

The event code is not valid.


### -field GetProperty

Represents <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_get_property.md">IOCTL_POINT_OF_SERVICE_GET_PROPERTY</a>.


### -field SetProperty

Represents <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_set_property.md">IOCTL_POINT_OF_SERVICE_SET_PROPERTY</a>.


### -field ClaimDevice

Represents <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_claim_device.md">IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE</a>.


### -field ReleaseDevice

Represents <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_release_device.md">IOCTL_POINT_OF_SERVICE_RELEASE_DEVICE</a>.


### -field RetainDevice

Represents <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_retain_device.md">IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE</a>.


### -field RetrieveStatistics

Represents <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_retrieve_statistics.md">IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS</a>.


### -field ResetStatistics

Represents <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_reset_statistics.md">IOCTL_POINT_OF_SERVICE_RESET_STATISTICS</a>.


### -field UpdateStatistics

Represents <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_update_statistics.md">IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS</a>.


### -field CheckHealth

Represents <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_check_health.md">IOCTL_POINT_OF_SERVICE_CHECK_HEALTH</a>.


### -field GetDeviceBasics

Represents <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_get_device_basics.md">IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS</a>.


### -field BarcodeScannerInjectEvent

Unused.


### -field MsrRetrieveDeviceAuthentication

Represents <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_msr_retrieve_device_authentication.md">IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION</a>.


### -field MsrAuthenticateDevice

Represents <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_msr_authenticate_device.md">IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE</a>.


### -field MsrDeAuthenticateDevice

Represents <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_msr_deauthenticate_device.md">IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE</a>.


### -field MsrUpdateKey

Represents <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_msr_update_key.md">IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY</a>.


### -field StartBarcodeScannerSoftwareTrigger


### -field StopBarcodeScannerSoftwareTrigger


### -field PrinterClearOutput


### -field PrinterSlipWaitForPaperInserted


### -field PrinterSlipWaitForPaperRemoved


### -field PrinterChangePrintSide


### -field PrinterCutPaper


### -field PrinterDrawRuledLine


### -field PrinterSlipOpenJaws


### -field PrinterSlipCloseJaws


### -field PrinterMarkFeed


### -field PrinterPageModePrint


### -field PrinterPrintBarcode


### -field PrinterPrintMemoryBitmapStart


### -field PrinterPrintMemoryBitmapFill


### -field PrinterPrintNormal


### -field PrinterRotatePrint


### -field PrinterSetBitmapStart


### -field PrinterSetBitmapFill


### -field PrinterTransactionPrint


### -field PrinterValidateData


### -field PrinterPrintSavedBitmap


### -field CashDrawerOpenDrawer


### -field CashDrawerCreateDrawerCloseAlarm


### -field CashDrawerCancelWait


### -field ConnectRemotePosDevice


### -field PrinterWaitForJobComplete


### -field LineDisplayCreateWindow


### -field LineDisplayDestroyWindow


### -field LineDisplayRefreshWindow


### -field LineDisplayWindowDisplayText


### -field LineDisplayWindowDisplayTextAt


### -field LineDisplayWindowScrollText


### -field LineDisplayWindowClearText


### -field LineDisplayWindowDisplayBitmap


### -field LineDisplaySetBitmap


### -field LineDisplaySetDescriptor


### -field LineDisplayClearDescriptors


### -field LineDisplayDefineGlyph


### -field LineDisplayReadCharacterAtCursor


### -field BarcodeScannerGetSymbologyAttributes


### -field BarcodeScannerSetSymbologyAttributes


### -field _MaxDeviceControlType


## -remarks



This enumeration provides values for each IOCTL that you can send to the device driver. It is a convenient way to indicate which IOCTL to dispatch when calling functions like <b>SendDeviceCommand()</b>.



