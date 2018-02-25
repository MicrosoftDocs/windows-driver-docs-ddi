---
UID: NE:pointofservicedriverinterface._PosPropertyId
title: "_PosPropertyId"
author: windows-driver-content
description: This enumeration defines the property identifiers for the properties that device drivers need to handle to be considered a barcode scanner or a magnetic strip reader (MSR).
old-location: pos\pospropertyid.htm
old-project: pos
ms.assetid: 82864db1-ee0a-4d41-a516-4e04befd2e89
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, BarcodeScannerActiveProfile, BarcodeScannerActiveSymbologies, BarcodeScannerCapabilities, BarcodeScannerIsDecodeDataEnabled, BarcodeScannerSupportedProfiles, BarcodeScannerSupportedSymbologies, I, IsDisabledOnDataReceived, IsEnabled, MagneticStripeReaderCapabilities, MagneticStripeReaderDataEncryptionAlgorithm, MagneticStripeReaderDeviceAuthenticationProtocol, MagneticStripeReaderErrorReportingType, MagneticStripeReaderIsDecodeDataEnabled, MagneticStripeReaderIsDeviceAuthenticated, MagneticStripeReaderIsTransmitSentinelsEnabled, MagneticStripeReaderSupportedCardTypes, MagneticStripeReaderTracksToRead, P, PosPropertyId, PosPropertyId enumeration, _, _PosPropertyId, d, e, o, p, pointofservicedriverinterface/BarcodeScannerActiveProfile, pointofservicedriverinterface/BarcodeScannerActiveSymbologies, pointofservicedriverinterface/BarcodeScannerCapabilities, pointofservicedriverinterface/BarcodeScannerIsDecodeDataEnabled, pointofservicedriverinterface/BarcodeScannerSupportedProfiles, pointofservicedriverinterface/BarcodeScannerSupportedSymbologies, pointofservicedriverinterface/IsDisabledOnDataReceived, pointofservicedriverinterface/IsEnabled, pointofservicedriverinterface/MagneticStripeReaderCapabilities, pointofservicedriverinterface/MagneticStripeReaderDataEncryptionAlgorithm, pointofservicedriverinterface/MagneticStripeReaderDeviceAuthenticationProtocol, pointofservicedriverinterface/MagneticStripeReaderErrorReportingType, pointofservicedriverinterface/MagneticStripeReaderIsDecodeDataEnabled, pointofservicedriverinterface/MagneticStripeReaderIsDeviceAuthenticated, pointofservicedriverinterface/MagneticStripeReaderIsTransmitSentinelsEnabled, pointofservicedriverinterface/MagneticStripeReaderSupportedCardTypes, pointofservicedriverinterface/MagneticStripeReaderTracksToRead, pointofservicedriverinterface/PosPropertyId, pos.pospropertyid, r, s, t, y"
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
-	PosPropertyId
product: Windows
targetos: Windows
req.typenames: PosPropertyId
---

# _PosPropertyId enumeration


## -description


This enumeration defines the property identifiers for the properties that device drivers need to handle to be considered a barcode scanner or a magnetic strip reader (MSR).


## -syntax


````
typedef enum _PosPropertyId { 
  IsEnabled                                         = 1,
  IsDisabledOnDataReceived                          = 4,
  BarcodeScannerIsDecodeDataEnabled                 = 5,
  BarcodeScannerCapabilities                        = 6,
  BarcodeScannerSupportedSymbologies                = 7,
  BarcodeScannerActiveSymbologies                   = 8,
  BarcodeScannerSupportedProfiles                   = 9,
  BarcodeScannerActiveProfile                       = 10,
  MagneticStripeReaderIsDecodeDataEnabled           = 11,
  MagneticStripeReaderCapabilities                  = 12,
  MagneticStripeReaderSupportedCardTypes            = 13,
  MagneticStripeReaderDeviceAuthenticationProtocol  = 14,
  MagneticStripeReaderErrorReportingType            = 15,
  MagneticStripeReaderTracksToRead                  = 16,
  MagneticStripeReaderIsTransmitSentinelsEnabled    = 17,
  MagneticStripeReaderIsDeviceAuthenticated         = 18,
  MagneticStripeReaderDataEncryptionAlgorithm       = 19
} PosPropertyId;
````


## -enum-fields




### -field IsEnabled

Indicates whether the device is enabled. An enabled device is expected to be powered on and fully functional. In a disabled state, the device is not expected to generate input and can be powered down. (Read/Write).


### -field IsDisabledOnDataReceived

Indicates whether to disable the device after each scan event. This allows the hardware to enter an idle power-saving mode as frequently as possible. (Read/Write).


### -field PowerState


### -field BarcodeScannerIsDecodeDataEnabled

When set to <b>TRUE</b>, the driver must return decoded bar code data in the form of <b>ScanDataLabel</b> in addition to <b>ScanData</b> when raising a data received event. Decoded barcode data typically only contains data from the scanner with header information, scanner generated symbol character, and length identification removed. (Read/Write).


### -field BarcodeScannerCapabilities

Contains information about what functionality the barcode scanner supports. For example, a barcode scanner may support imaging and standard power reporting but not statistics updating and reporting. For more information about the values for barcode capabilities, see <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posbarcodescannercapabilitiestype.md">PosBarcodeScannerCapabilitiesType</a>. (Read-only).


### -field BarcodeScannerSupportedSymbologies

Contains an array representing the complete list of symbologies that the barcode scanner is capable of reading. Also returns the number of bytes required for the array of symbologies. For symbology definitions, see <a href="..\pointofservicecommontypes\ne-pointofservicecommontypes-_barcodesymbology.md">BarcodeSymbology</a>. (Read-only).


### -field BarcodeScannerActiveSymbologies

Indicates the symbologies that the barcode scanner is actively handling. (Write-only). For symbology definitions, see <a href="..\pointofservicecommontypes\ne-pointofservicecommontypes-_barcodesymbology.md">BarcodeSymbology</a>.


### -field BarcodeScannerSupportedProfiles

Returns the list of supported driver-defined device configuration profiles. (Read-only).


### -field BarcodeScannerActiveProfile

Sets the active device configuration profile. Configure the driver using one of the driver- or manufacturer-defined profiles in the list returned by the <b>BarcodeScannerSupportedProfiles</b> property. (Write-Only). For example, you may have one profile for warehouse staff and another profile for the sales department. Each profile is expected to configure the device based on the driver or manufacturer definition.


### -field MagneticStripeReaderIsDecodeDataEnabled

Indicates whether to provide raw or decoded data from the most recently swiped card. If decoded data is provided to the application, set to <b>true</b>; otherwise, set to <b>false</b>. (Read/write).


### -field MagneticStripeReaderCapabilities

Returns a <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posmagneticstripereadercapabilitiestype.md">PosMagneticStripeReaderCapabilitiesType</a> that describes the capabilities of the MSR. (Read-Only).


### -field MagneticStripeReaderSupportedCardTypes

Returns an array of <a href="..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_msrcardtype.md">MsrCardType</a>s supported by the MSR. (Read-only).


### -field MagneticStripeReaderDeviceAuthenticationProtocol

The driver must return a <a href="..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_msrauthenticationprotocol.md">MsrAuthenticationProtocolType</a> that describes the device authentication protocol supported by the MSR. (Read-only).


### -field MagneticStripeReaderErrorReportingType

Specifies the level of error reporting that the MSR supports. For more information about the values for error reporting levels, see <a href="..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_msrerrorreportingtype.md">MsrErrorReportingType</a>. (Read/write).


### -field MagneticStripeReaderTracksToRead

Specifies which tracks the application will receive following a card swipe. Does not indicate the capability of the device hardware; instead, it is an application-configurable property representing the tracks to be read. For more information about track values, see <a href="..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_msrtrackids.md">MsrTrackIds</a>. (Read/write).


### -field MagneticStripeReaderIsTransmitSentinelsEnabled

Indicates whether the track data contains start and end sentinel values. (Read/write).


### -field MagneticStripeReaderIsDeviceAuthenticated

Indicates whether the device is authenticated. (Read-only).


### -field MagneticStripeReaderDataEncryptionAlgorithm

Specifies the <a href="..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_msrdataencryption.md">MsrDataEncryption</a> that will be used to encrypt the track data. (Read/write).


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

<a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_set_property.md">IOCTL_POINT_OF_SERVICE_SET_PROPERTY</a>



<a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_get_property.md">IOCTL_POINT_OF_SERVICE_GET_PROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [pos\pos]:%20PosPropertyId enumeration%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

