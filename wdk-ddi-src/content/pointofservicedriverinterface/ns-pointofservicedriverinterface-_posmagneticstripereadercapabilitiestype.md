---
UID: NS:pointofservicedriverinterface._PosMagneticStripeReaderCapabilitiesType
title: _PosMagneticStripeReaderCapabilitiesType (pointofservicedriverinterface.h)
description: This structure defines the kinds of magnetic stripe reader (MSR) capabilities that a device supports, such as whether the device supports track data masking.
old-location: pos\posmagneticstripereadercapabilitiestype.htm
tech.root: pos
ms.assetid: 8f5ad241-a145-468d-bd69-7956985152b5
ms.date: 02/23/2018
ms.keywords: PosMagneticStripeReaderCapabilitiesType, PosMagneticStripeReaderCapabilitiesType structure, _PosMagneticStripeReaderCapabilitiesType, pointofservicedriverinterface/PosMagneticStripeReaderCapabilitiesType, pos.posmagneticstripereadercapabilitiestype
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- PointOfServiceDriverInterface.h
api_name:
- PosMagneticStripeReaderCapabilitiesType
product:
- Windows
targetos: Windows
req.typenames: PosMagneticStripeReaderCapabilitiesType
---

# _PosMagneticStripeReaderCapabilitiesType structure


## -description


This structure defines the kinds of magnetic stripe reader (MSR) capabilities that a device supports, such as whether the device supports track data masking.


## -struct-fields




### -field PowerReportingType

Indicates the type of power reporting that is supported by the device.


### -field IsStatisticsReportingSupported

Indicates whether the device supports <a href="https://msdn.microsoft.com/library/windows/hardware/dn772120">IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS</a>.


### -field IsStatisticsUpdatingSupported

Indicates whether the device supports <a href="https://msdn.microsoft.com/library/windows/hardware/dn772126">IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS</a>.


### -field CardAuthenticationLength

The length, in bytes, of the name of the type of authentication that the device uses.


### -field SupportedEncryptionAlgorithms

The supported encryption algorithm. See <a href="https://msdn.microsoft.com/library/windows/hardware/dn772169">MsrDataEncryption</a>.


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

