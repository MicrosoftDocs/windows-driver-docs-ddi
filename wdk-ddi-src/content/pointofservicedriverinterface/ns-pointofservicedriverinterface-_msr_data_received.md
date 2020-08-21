---
UID: NS:pointofservicedriverinterface._MSR_DATA_RECEIVED
title: _MSR_DATA_RECEIVED (pointofservicedriverinterface.h)
description: This structure contains the data read from a swiped magnetic stripe card.
old-location: pos\msr_data_received.htm
tech.root: pos
ms.assetid: f103724c-25c4-4dec-a7a3-9713440ca833
ms.date: 02/23/2018
keywords: ["MSR_DATA_RECEIVED structure"]
ms.keywords: "*PMSR_DATA_RECEIVED, MSR_DATA_RECEIVED, MSR_DATA_RECEIVED structure, PMSR_DATA_RECEIVED, PMSR_DATA_RECEIVED structure pointer, _MSR_DATA_RECEIVED, pointofservicedriverinterface/MSR_DATA_RECEIVED, pointofservicedriverinterface/PMSR_DATA_RECEIVED, pos.msr_data_received"
f1_keywords:
 - "pointofservicedriverinterface/MSR_DATA_RECEIVED"
 - "MSR_DATA_RECEIVED"
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
- MSR_DATA_RECEIVED
targetos: Windows
req.typenames: MSR_DATA_RECEIVED, *PMSR_DATA_RECEIVED
---

# _MSR_DATA_RECEIVED structure


## -description


This structure contains the data read from a swiped magnetic stripe card.


## -struct-fields




### -field CardType

Type of card that was swiped.


### -field Track1EncryptedDataLength

The amount of encrypted track 1 data, in bytes, that is stored in **Track1EncryptedData[MSR_TRACK_SIZE].**


### -field Track2EncryptedDataLength

The amount of encrypted track 2 data, in bytes, that is stored in **Track2EncryptedData[MSR_TRACK_SIZE].**


### -field Track3EncryptedDataLength

The amount of encrypted track 3 data, in bytes, that is stored in **Track3EncryptedData[MSR_TRACK_SIZE].**


### -field Track4EncryptedDataLength

The amount of encrypted track 4 data, in bytes, that is stored in **Track4EncryptedData[MSR_TRACK_SIZE].**


### -field Track1EncryptedData

The encrypted data read from track 1 of the swiped card.


### -field Track2EncryptedData

The encrypted data read from track 2 of the swiped card.


### -field Track3EncryptedData

The encrypted data read from track 3 of the swiped card.


### -field Track4EncryptedData

The encrypted data read from track 4 of the swiped card.


### -field Track1MaskedDataLength

The amount of masked track 1 data, in bytes, that is stored in **Track1MaskedData[MSR_TRACK_SIZE]**.


### -field Track2MaskedDataLength

The amount of masked track 2 data, in bytes, that is stored in **Track2MaskedData[MSR_TRACK_SIZE]**.


### -field Track3MaskedDataLength

The amount of masked track 3 data, in bytes, that is stored in **Track3MaskedData[MSR_TRACK_SIZE]**.


### -field Track4MaskedDataLength

The amount of masked track 4 data, in bytes, that is stored in **Track4MaskedData[MSR_TRACK_SIZE]**.


### -field Track1MaskedData

The masked data read from track 1 of the swiped card.


### -field Track2MaskedData

The masked data read from track 2 of the swiped card.


### -field Track3MaskedData

The masked data read from track 3 of the swiped card.


### -field Track4MaskedData

The masked data read from track 4 of the swiped card.


### -field Track1DiscretionaryDataLength

The amount of discretionary track 1 data, in bytes, that is stored in **Track1DiscretionaryData[MSR_TRACK_SIZE]**.


### -field Track2DiscretionaryDataLength

The amount of discretionary track 2 data, in bytes, that is stored in **Track2DiscretionaryData[MSR_TRACK_SIZE]**.


### -field Track1DiscretionaryData

The amount of discretionary  track 1 data, in bytes, that is stored in **Track1DiscretionaryData[MSR_TRACK_SIZE]**.


### -field Track2DiscretionaryData

The amount of discretionary track 2 data, in bytes, that is stored in **Track1DiscretionaryData[MSR_TRACK_SIZE]**.


### -field CardAuthenicationDataLength

The amount of encrypted card authentication data, in bytes, that is stored in **CardAuthenicationData[MSR_CARD_AUTHENTICATION_DATA_SIZE]**. May include padding.


### -field CardAuthenticationDataAbsoluteLength

The amount of card authentication data, in bytes, before encryption. This value may be used to remove padding on decryption.


### -field CardAuthenicationData

Authentication data read from the swiped card.


### -field AdditionalSecurityInformationLength

The amount of additional security information, in bytes, stored in **AdditionalSecurityInformation[MSR_ADDITIONAL_SECURITY_INFORMATION_SIZE]**.


### -field AdditionalSecurityInformation

Additional security information read from the swiped card.

