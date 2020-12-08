---
UID: NS:pointofservicedriverinterface._PosMagneticStripeReaderCapabilitiesType
title: _PosMagneticStripeReaderCapabilitiesType (pointofservicedriverinterface.h)
description: This structure defines the kinds of magnetic stripe reader (MSR) capabilities that a device supports, such as whether the device supports track data masking.
old-location: pos\posmagneticstripereadercapabilitiestype.htm
tech.root: pos
ms.date: 02/23/2018
keywords: ["PosMagneticStripeReaderCapabilitiesType structure"]
ms.keywords: PosMagneticStripeReaderCapabilitiesType, PosMagneticStripeReaderCapabilitiesType structure, _PosMagneticStripeReaderCapabilitiesType, pointofservicedriverinterface/PosMagneticStripeReaderCapabilitiesType, pos.posmagneticstripereadercapabilitiestype
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
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
req.typenames: PosMagneticStripeReaderCapabilitiesType
f1_keywords:
 - _PosMagneticStripeReaderCapabilitiesType
 - pointofservicedriverinterface/_PosMagneticStripeReaderCapabilitiesType
 - PosMagneticStripeReaderCapabilitiesType
 - pointofservicedriverinterface/PosMagneticStripeReaderCapabilitiesType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - PointOfServiceDriverInterface.h
api_name:
 - PosMagneticStripeReaderCapabilitiesType
---

# _PosMagneticStripeReaderCapabilitiesType structure


## -description

This structure defines the kinds of magnetic stripe reader (MSR) capabilities that a device supports, such as whether the device supports track data masking.

## -struct-fields

### -field PowerReportingType

Indicates the type of power reporting that is supported by the device.

### -field IsStatisticsReportingSupported

Indicates whether the device supports <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_retrieve_statistics">IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS</a>.

### -field IsStatisticsUpdatingSupported

Indicates whether the device supports <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_update_statistics">IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS</a>.

### -field CardAuthenticationLength

The length, in bytes, of the name of the type of authentication that the device uses.

### -field SupportedEncryptionAlgorithms

The supported encryption algorithm. See <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ne-pointofservicedriverinterface-_msrdataencryption">MsrDataEncryption</a>.

### -field AuthenticationLevel

The authentication level that the device supports.

### -field IsIsoSupported

Indicates whether the device supports ISO cards.

### -field IsJisOneSupported

Indicates whether device supports JIS Type-I cards.

### -field IsJisTwoSupported

Indicates whether device supports JIS Type-II cards.

### -field IsTrackDataMaskingSupported

Indicates whether the device is capable of masking track data.

### -field IsTransmitSentinelsSupported

Indicates whether the devices is able to transmit start and end sentinels.
