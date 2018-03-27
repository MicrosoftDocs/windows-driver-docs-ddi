---
UID: NS:pointofservicedriverinterface._MSR_DATA_RECEIVED
title: "_MSR_DATA_RECEIVED"
author: windows-driver-content
description: This structure contains the data read from a swiped magnetic stripe card.
old-location: pos\msr_data_received.htm
old-project: pos
ms.assetid: f103724c-25c4-4dec-a7a3-9713440ca833
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PMSR_DATA_RECEIVED, MSR_DATA_RECEIVED, MSR_DATA_RECEIVED structure, PMSR_DATA_RECEIVED, PMSR_DATA_RECEIVED structure pointer, _MSR_DATA_RECEIVED, pointofservicedriverinterface/MSR_DATA_RECEIVED, pointofservicedriverinterface/PMSR_DATA_RECEIVED, pos.msr_data_received"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	PointOfServiceDriverInterface.h
api_name:
-	MSR_DATA_RECEIVED
product: Windows
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

The amount of encrypted track 1 data, in bytes, that is stored in <b>Track1EncryptedData[MSR_TRACK_SIZE].</b>


### -field Track2EncryptedDataLength

The amount of encrypted track 2 data, in bytes, that is stored in <b>Track2EncryptedData[MSR_TRACK_SIZE].</b>


### -field Track3EncryptedDataLength

The amount of encrypted track 3 data, in bytes, that is stored in <b>Track3EncryptedData[MSR_TRACK_SIZE].</b>


### -field Track4EncryptedDataLength

The amount of encrypted track 4 data, in bytes, that is stored in <b>Track4EncryptedData[MSR_TRACK_SIZE].</b>


### -field Track1EncryptedData

The encrypted data read from track 1 of the swiped card.


### -field Track2EncryptedData

The encrypted data read from track 2 of the swiped card.


### -field Track3EncryptedData

The encrypted data read from track 3 of the swiped card.


### -field Track4EncryptedData

The encrypted data read from track 4 of the swiped card.


### -field Track1MaskedDataLength

The amount of masked track 1 data, in bytes, that is stored in <b>Track1MaskedData[MSR_TRACK_SIZE]</b>.


### -field Track2MaskedDataLength

The amount of masked track 2 data, in bytes, that is stored in <b>Track2MaskedData[MSR_TRACK_SIZE]</b>.


### -field Track3MaskedDataLength

The amount of masked track 3 data, in bytes, that is stored in <b>Track3MaskedData[MSR_TRACK_SIZE]</b>.


### -field Track4MaskedDataLength

The amount of masked track 4 data, in bytes, that is stored in <b>Track4MaskedData[MSR_TRACK_SIZE]</b>.


### -field Track1MaskedData

The masked data read from track 1 of the swiped card.


### -field Track2MaskedData

The masked data read from track 2 of the swiped card.


### -field Track3MaskedData

The masked data read from track 3 of the swiped card.


### -field Track4MaskedData

The masked data read from track 4 of the swiped card.


### -field Track1DiscretionaryDataLength

The amount of discretionary track 1 data, in bytes, that is stored in <b>Track1DiscretionaryData[MSR_TRACK_SIZE]</b>.


### -field Track2DiscretionaryDataLength

The amount of discretionary track 2 data, in bytes, that is stored in <b>Track2DiscretionaryData[MSR_TRACK_SIZE]</b>.


### -field Track1DiscretionaryData

The amount of discretionary  track 1 data, in bytes, that is stored in <b>Track1DiscretionaryData[MSR_TRACK_SIZE]</b>.


### -field Track2DiscretionaryData

The amount of discretionary track 2 data, in bytes, that is stored in <b>Track1DiscretionaryData[MSR_TRACK_SIZE]</b>.


### -field CardAuthenicationDataLength

The amount of encrypted card authentication data, in bytes, that is stored in <b>CardAuthenicationData[MSR_CARD_AUTHENTICATION_DATA_SIZE]</b>. May include padding.


### -field CardAuthenticationDataAbsoluteLength

The amount of card authentication data, in bytes, before encryption. This value may be used to remove padding on decryption.


### -field CardAuthenicationData

Authentication data read from the swiped card.


### -field AdditionalSecurityInformationLength

The amount of additional security information, in bytes, stored in <b>AdditionalSecurityInformation[MSR_ADDITIONAL_SECURITY_INFORMATION_SIZE]</b>.


### -field AdditionalSecurityInformation

Additional security information read from the swiped card.

