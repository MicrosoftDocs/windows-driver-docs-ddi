---
UID: NE:pointofservicedriverinterface._PosPropertyId
title: PosPropertyId (pointofservicedriverinterface.h)
description: This enumeration defines the property identifiers for the properties that device drivers need to handle to be considered a barcode scanner or a magnetic strip reader (MSR).
tech.root: pos
ms.date: 04/19/2022
keywords: ["PosPropertyId enumeration"]
ms.keywords: BarcodeScannerActiveProfile, BarcodeScannerActiveSymbologies, BarcodeScannerCapabilities, BarcodeScannerIsDecodeDataEnabled, BarcodeScannerSupportedProfiles, BarcodeScannerSupportedSymbologies, IsDisabledOnDataReceived, IsEnabled, MagneticStripeReaderCapabilities, MagneticStripeReaderDataEncryptionAlgorithm, MagneticStripeReaderDeviceAuthenticationProtocol, MagneticStripeReaderErrorReportingType, MagneticStripeReaderIsDecodeDataEnabled, MagneticStripeReaderIsDeviceAuthenticated, MagneticStripeReaderIsTransmitSentinelsEnabled, MagneticStripeReaderSupportedCardTypes, MagneticStripeReaderTracksToRead, PosPropertyId, PosPropertyId enumeration, _PosPropertyId, pointofservicedriverinterface/BarcodeScannerActiveProfile, pointofservicedriverinterface/BarcodeScannerActiveSymbologies, pointofservicedriverinterface/BarcodeScannerCapabilities, pointofservicedriverinterface/BarcodeScannerIsDecodeDataEnabled, pointofservicedriverinterface/BarcodeScannerSupportedProfiles, pointofservicedriverinterface/BarcodeScannerSupportedSymbologies, pointofservicedriverinterface/IsDisabledOnDataReceived, pointofservicedriverinterface/IsEnabled, pointofservicedriverinterface/MagneticStripeReaderCapabilities, pointofservicedriverinterface/MagneticStripeReaderDataEncryptionAlgorithm, pointofservicedriverinterface/MagneticStripeReaderDeviceAuthenticationProtocol, pointofservicedriverinterface/MagneticStripeReaderErrorReportingType, pointofservicedriverinterface/MagneticStripeReaderIsDecodeDataEnabled, pointofservicedriverinterface/MagneticStripeReaderIsDeviceAuthenticated, pointofservicedriverinterface/MagneticStripeReaderIsTransmitSentinelsEnabled, pointofservicedriverinterface/MagneticStripeReaderSupportedCardTypes, pointofservicedriverinterface/MagneticStripeReaderTracksToRead, pointofservicedriverinterface/PosPropertyId, pos.pospropertyid
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
req.typenames: PosPropertyId
f1_keywords:
 - _PosPropertyId
 - pointofservicedriverinterface/_PosPropertyId
 - PosPropertyId
 - pointofservicedriverinterface/PosPropertyId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pointofservicedriverinterface.h
api_name:
 - _PosPropertyId
 - PosPropertyId
---

## -description

This enumeration defines the property identifiers for the properties that device drivers need to handle to be considered a barcode scanner or a magnetic strip reader (MSR).

## -enum-fields

### -field IsEnabled

Indicates whether the device is enabled. An enabled device is expected to be powered on and fully functional. In a disabled state, the device is not expected to generate input and can be powered down. (Read/Write).

### -field IsDisabledOnDataReceived

Indicates whether to disable the device after each scan event. This allows the hardware to enter an idle power-saving mode as frequently as possible. (Read/Write).

### -field PowerState

Reports the current power state of the device.

### -field BarcodeScannerIsDecodeDataEnabled

When set to **TRUE**, the driver must return decoded bar code data in the form of **ScanDataLabel** in addition to **ScanData** when raising a data received event. Decoded barcode data typically only contains data from the scanner with header information, scanner generated symbol character, and length identification removed. (Read/Write).

### -field BarcodeScannerCapabilities

Contains information about what functionality the barcode scanner supports. For example, a barcode scanner may support imaging and standard power reporting but not statistics updating and reporting. For more information about the values for barcode capabilities, see [PosBarcodeScannerCapabilitiesType](./ns-pointofservicedriverinterface-_posbarcodescannercapabilitiestype.md). (Read-only).

### -field BarcodeScannerSupportedSymbologies

Contains an array representing the complete list of symbologies that the barcode scanner is capable of reading. Also returns the number of bytes required for the array of symbologies. For symbology definitions, see [BarcodeSymbology](../pointofservicecommontypes/ne-pointofservicecommontypes-_barcodesymbology.md). (Read-only).

### -field BarcodeScannerActiveSymbologies

Indicates the symbologies that the barcode scanner is actively handling. (Write-only). For symbology definitions, see [BarcodeSymbology](../pointofservicecommontypes/ne-pointofservicecommontypes-_barcodesymbology.md).

### -field BarcodeScannerSupportedProfiles

Returns the list of supported driver-defined device configuration profiles. (Read-only).

### -field BarcodeScannerActiveProfile

Sets the active device configuration profile. Configure the driver using one of the driver- or manufacturer-defined profiles in the list returned by the **BarcodeScannerSupportedProfiles** property. (Write-Only). For example, you may have one profile for warehouse staff and another profile for the sales department. Each profile is expected to configure the device based on the driver or manufacturer definition.

### -field MagneticStripeReaderIsDecodeDataEnabled

Indicates whether to provide raw or decoded data from the most recently swiped card. If decoded data is provided to the application, set to **true**; otherwise, set to **false**. (Read/write).

### -field MagneticStripeReaderCapabilities

Returns a [PosMagneticStripeReaderCapabilitiesType](./ns-pointofservicedriverinterface-_posmagneticstripereadercapabilitiestype.md) that describes the capabilities of the MSR. (Read-Only).

### -field MagneticStripeReaderSupportedCardTypes

Returns an array of [MsrCardType](./ne-pointofservicedriverinterface-_msrcardtype.md)s supported by the MSR. (Read-only).

### -field MagneticStripeReaderDeviceAuthenticationProtocol

The driver must return a [MsrAuthenticationProtocolType](/previous-versions/windows/hardware/previsioning-framework/dn772165(v=vs.85)) that describes the device authentication protocol supported by the MSR. (Read-only).

### -field MagneticStripeReaderErrorReportingType

Specifies the level of error reporting that the MSR supports. For more information about the values for error reporting levels, see [MsrErrorReportingType](./ne-pointofservicedriverinterface-_msrerrorreportingtype.md). (Read/write).

### -field MagneticStripeReaderTracksToRead

Specifies which tracks the application will receive following a card swipe. Does not indicate the capability of the device hardware; instead, it is an application-configurable property representing the tracks to be read. For more information about track values, see [MsrTrackIds](./ne-pointofservicedriverinterface-_msrtrackids.md). (Read/write).

### -field MagneticStripeReaderIsTransmitSentinelsEnabled

Indicates whether the track data contains start and end sentinel values. (Read/write).

### -field MagneticStripeReaderIsDeviceAuthenticated

Indicates whether the device is authenticated. (Read-only).

### -field MagneticStripeReaderDataEncryptionAlgorithm

Specifies the [MsrDataEncryption](./ne-pointofservicedriverinterface-_msrdataencryption.md) that will be used to encrypt the track data. (Read/write).

### -field BarcodeScannerVideoDeviceId

Defines the **BarcodeScannerVideoDeviceId** constant.

## -see-also

[IOCTL_POINT_OF_SERVICE_GET_PROPERTY](./ni-pointofservicedriverinterface-ioctl_point_of_service_get_property.md)

[IOCTL_POINT_OF_SERVICE_SET_PROPERTY](./ni-pointofservicedriverinterface-ioctl_point_of_service_set_property.md)