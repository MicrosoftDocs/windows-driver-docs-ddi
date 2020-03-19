---
UID: NE:pointofservicedriverinterface._PosPropertyId
title: _PosPropertyId (pointofservicedriverinterface.h)
description: This enumeration defines the property identifiers for the properties that device drivers need to handle to be considered a barcode scanner or a magnetic strip reader (MSR).
old-location: pos\pospropertyid.htm
tech.root: pos
ms.assetid: 82864db1-ee0a-4d41-a516-4e04befd2e89
ms.date: 02/23/2018
keywords: ["_PosPropertyId enumeration"]
ms.keywords: BarcodeScannerActiveProfile, BarcodeScannerActiveSymbologies, BarcodeScannerCapabilities, BarcodeScannerIsDecodeDataEnabled, BarcodeScannerSupportedProfiles, BarcodeScannerSupportedSymbologies, IsDisabledOnDataReceived, IsEnabled, MagneticStripeReaderCapabilities, MagneticStripeReaderDataEncryptionAlgorithm, MagneticStripeReaderDeviceAuthenticationProtocol, MagneticStripeReaderErrorReportingType, MagneticStripeReaderIsDecodeDataEnabled, MagneticStripeReaderIsDeviceAuthenticated, MagneticStripeReaderIsTransmitSentinelsEnabled, MagneticStripeReaderSupportedCardTypes, MagneticStripeReaderTracksToRead, PosPropertyId, PosPropertyId enumeration, _PosPropertyId, pointofservicedriverinterface/BarcodeScannerActiveProfile, pointofservicedriverinterface/BarcodeScannerActiveSymbologies, pointofservicedriverinterface/BarcodeScannerCapabilities, pointofservicedriverinterface/BarcodeScannerIsDecodeDataEnabled, pointofservicedriverinterface/BarcodeScannerSupportedProfiles, pointofservicedriverinterface/BarcodeScannerSupportedSymbologies, pointofservicedriverinterface/IsDisabledOnDataReceived, pointofservicedriverinterface/IsEnabled, pointofservicedriverinterface/MagneticStripeReaderCapabilities, pointofservicedriverinterface/MagneticStripeReaderDataEncryptionAlgorithm, pointofservicedriverinterface/MagneticStripeReaderDeviceAuthenticationProtocol, pointofservicedriverinterface/MagneticStripeReaderErrorReportingType, pointofservicedriverinterface/MagneticStripeReaderIsDecodeDataEnabled, pointofservicedriverinterface/MagneticStripeReaderIsDeviceAuthenticated, pointofservicedriverinterface/MagneticStripeReaderIsTransmitSentinelsEnabled, pointofservicedriverinterface/MagneticStripeReaderSupportedCardTypes, pointofservicedriverinterface/MagneticStripeReaderTracksToRead, pointofservicedriverinterface/PosPropertyId, pos.pospropertyid
f1_keywords:
 - "pointofservicedriverinterface/PosPropertyId"
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
- PosPropertyId
product:
- Windows
targetos: Windows
req.typenames: PosPropertyId
---

# _PosPropertyId enumeration


## -description


This enumeration defines the property identifiers for the properties that device drivers need to handle to be considered a barcode scanner or a magnetic strip reader (MSR).


## -enum-fields




### -field IsEnabled

Indicates whether the device is enabled. An enabled device is expected to be powered on and fully functional. In a disabled state, the device is not expected to generate input and can be powered down. (Read/Write).


### -field IsDisabledOnDataReceived

Indicates whether to disable the device after each scan event. This allows the hardware to enter an idle power-saving mode as frequently as possible. (Read/Write).


### -field PowerState


### -field BarcodeScannerIsDecodeDataEnabled

When set to <b>TRUE</b>, the driver must return decoded bar code data in the form of <b>ScanDataLabel</b> in addition to <b>ScanData</b> when raising a data received event. Decoded barcode data typically only contains data from the scanner with header information, scanner generated symbol character, and length identification removed. (Read/Write).


### -field BarcodeScannerCapabilities

Contains information about what functionality the barcode scanner supports. For example, a barcode scanner may support imaging and standard power reporting but not statistics updating and reporting. For more information about the values for barcode capabilities, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ns-pointofservicedriverinterface-_posbarcodescannercapabilitiestype">PosBarcodeScannerCapabilitiesType</a>. (Read-only).


### -field BarcodeScannerSupportedSymbologies

Contains an array representing the complete list of symbologies that the barcode scanner is capable of reading. Also returns the number of bytes required for the array of symbologies. For symbology definitions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicecommontypes/ne-pointofservicecommontypes-_barcodesymbology">BarcodeSymbology</a>. (Read-only).


### -field BarcodeScannerActiveSymbologies

Indicates the symbologies that the barcode scanner is actively handling. (Write-only). For symbology definitions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicecommontypes/ne-pointofservicecommontypes-_barcodesymbology">BarcodeSymbology</a>.


### -field BarcodeScannerSupportedProfiles

Returns the list of supported driver-defined device configuration profiles. (Read-only).


### -field BarcodeScannerActiveProfile

Sets the active device configuration profile. Configure the driver using one of the driver- or manufacturer-defined profiles in the list returned by the <b>BarcodeScannerSupportedProfiles</b> property. (Write-Only). For example, you may have one profile for warehouse staff and another profile for the sales department. Each profile is expected to configure the device based on the driver or manufacturer definition.


### -field MagneticStripeReaderIsDecodeDataEnabled

Indicates whether to provide raw or decoded data from the most recently swiped card. If decoded data is provided to the application, set to <b>true</b>; otherwise, set to <b>false</b>. (Read/write).


### -field MagneticStripeReaderCapabilities

Returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ns-pointofservicedriverinterface-_posmagneticstripereadercapabilitiestype">PosMagneticStripeReaderCapabilitiesType</a> that describes the capabilities of the MSR. (Read-Only).


### -field MagneticStripeReaderSupportedCardTypes

Returns an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ne-pointofservicedriverinterface-_msrcardtype">MsrCardType</a>s supported by the MSR. (Read-only).


### -field MagneticStripeReaderDeviceAuthenticationProtocol

The driver must return a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn772165(v=vs.85)">MsrAuthenticationProtocolType</a> that describes the device authentication protocol supported by the MSR. (Read-only).


### -field MagneticStripeReaderErrorReportingType

Specifies the level of error reporting that the MSR supports. For more information about the values for error reporting levels, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ne-pointofservicedriverinterface-_msrerrorreportingtype">MsrErrorReportingType</a>. (Read/write).


### -field MagneticStripeReaderTracksToRead

Specifies which tracks the application will receive following a card swipe. Does not indicate the capability of the device hardware; instead, it is an application-configurable property representing the tracks to be read. For more information about track values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ne-pointofservicedriverinterface-_msrtrackids">MsrTrackIds</a>. (Read/write).


### -field MagneticStripeReaderIsTransmitSentinelsEnabled

Indicates whether the track data contains start and end sentinel values. (Read/write).


### -field MagneticStripeReaderIsDeviceAuthenticated

Indicates whether the device is authenticated. (Read-only).


### -field MagneticStripeReaderDataEncryptionAlgorithm

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ne-pointofservicedriverinterface-_msrdataencryption">MsrDataEncryption</a> that will be used to encrypt the track data. (Read/write).


### -field BarcodeScannerVideoDeviceId


### -field PrinterCapabilities


### -field PrinterCartridgeNotifyEnabled


### -field PrinterSupportedCharacterSets


### -field PrinterFlagWhenIdle


### -field PrinterFontTypefaceList


### -field PrinterMapCharacterSet


### -field PrinterRotateSpecial


### -field PrinterSupportedJournalLineChars


### -field PrinterSupportedReceiptLineChars


### -field PrinterSupportedReceiptBarcodeRotations


### -field PrinterSupportedReceiptBitmapRotations


### -field PrinterSupportedSlipLineChars


### -field PrinterSupportedSlipBarcodeRotations


### -field PrinterSupportedSlipBitmapRotations


### -field PrinterCharacterSet


### -field PrinterCoverOpen


### -field PrinterMapMode


### -field PrinterPageModeArea


### -field PrinterPageModeDescriptor


### -field PrinterPageModeHorizontalPosition


### -field PrinterPageModePrintArea


### -field PrinterPageModePrintDirection


### -field PrinterPageModeStation


### -field PrinterPageModeVerticalPosition


### -field PrinterJournalLineChars


### -field PrinterJournalLineHeight


### -field PrinterJournalLineSpacing


### -field PrinterJournalLineWidth


### -field PrinterJournalLetterQuality


### -field PrinterJournalPaperEmpty


### -field PrinterJournalPaperNearEnd


### -field PrinterJournalCartridgeState


### -field PrinterJournalCurrentCartridge


### -field PrinterReceiptLineChars


### -field PrinterReceiptLineHeight


### -field PrinterReceiptLineSpacing


### -field PrinterReceiptLineWidth


### -field PrinterReceiptLetterQuality


### -field PrinterReceiptPaperEmpty


### -field PrinterReceiptPaperNearEmpty


### -field PrinterReceiptSidewaysMaxLines


### -field PrinterReceiptSidewaysMaxChars


### -field PrinterReceiptLinesToPaperCut


### -field PrinterReceiptCartridgeState


### -field PrinterReceiptCurrentCartridge


### -field PrinterSlipLineChars


### -field PrinterSlipLineHeight


### -field PrinterSlipLineSpacing


### -field PrinterSlipLineWidth


### -field PrinterSlipLetterQuality


### -field PrinterSlipPaperEmpty


### -field PrinterSlipPaperNearEmpty


### -field PrinterSlipSidewaysMaxLines


### -field PrinterSlipSideWaysMaxChars


### -field PrinterSlipMaxLines


### -field PrinterSlipLinesNearEndToEnd


### -field PrinterSlipPrintside


### -field PrinterSlipCartridgeState


### -field PrinterSlipCurrentCartridge


### -field PrinterStatusProp


### -field CashDrawerIsDrawerOpened


### -field CashDrawerCapabilities


### -field CashDrawerStatusProp


### -field LineDisplayCapabilities


### -field LineDisplayCurrentWindow


### -field LineDisplayWindowSizeInCharacters


### -field LineDisplayWindowInterCharacterWaitInterval


### -field LineDisplayPhysicalDeviceName


### -field LineDisplayPhysicalDeviceDescription


### -field LineDisplayDeviceControlDescription


### -field LineDisplayDeviceControlVersion


### -field LineDisplayDeviceServiceVersion


### -field LineDisplayCursorTypeProperty


### -field LineDisplayCursorAutoUpdateEnabled


### -field LineDisplayCursorPosition


### -field LineDisplayScreenModeList


### -field LineDisplayScreenMode


### -field LineDisplayMaxBitmapSizeInPixels


### -field LineDisplayCharacterSetList


### -field LineDisplayDeviceBrightness


### -field LineDisplayBlinkRate


### -field LineDisplayCharacterSet


### -field LineDisplayMapCharacterSet


### -field LineDisplayGlyphSizeInPixels


### -field LineDisplayCustomGlyphList


### -field LineDisplayMarqueeFormat


### -field LineDisplayMarqueeRepeatWait


### -field LineDisplayMarqueeUnitWait


### -field LineDisplayMarqueeType




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_get_property">IOCTL_POINT_OF_SERVICE_GET_PROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_set_property">IOCTL_POINT_OF_SERVICE_SET_PROPERTY</a>
 

 

