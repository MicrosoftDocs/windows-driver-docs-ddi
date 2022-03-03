---
UID: NE:acxpin._ACX_JACK_CONNECTION_TYPE
tech.root: audio
title: ACX_JACK_CONNECTION_TYPE
ms.date: 02/17/2022
targetos: Windows
description: The ACX_JACK_CONNECTION_TYPE enumeration is used to describe the type of a physical connection jack.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxpin.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxpin.h
api_name:
 - _ACX_JACK_CONNECTION_TYPE
 - PACX_JACK_CONNECTION_TYPE
 - ACX_JACK_CONNECTION_TYPE
f1_keywords:
 - _ACX_JACK_CONNECTION_TYPE
 - acxpin/_ACX_JACK_CONNECTION_TYPE
 - PACX_JACK_CONNECTION_TYPE
 - acxpin/PACX_JACK_CONNECTION_TYPE
 - ACX_JACK_CONNECTION_TYPE
 - acxpin/ACX_JACK_CONNECTION_TYPE
dev_langs:
 - c++
---

## -description

The **ACX_JACK_CONNECTION_TYPE** enumeration is used by the [ACX_JACK_DESCRIPTION](ns-acxpin-acx_jack_description.md) structure to describe the type of a physical connection jack.

## -enum-fields

### -field AcxConnTypeUnknown

Indicates that the connection type is unknown.

### -field AcxConnType3Point5mm

Indicates that the connection type is a 3.5 millimeter jack.

### -field AcxConnTypeQuarter

Indicates that the connection type is a quarter-inch jack.

### -field AcxConnTypeAtapiInternal

Indicates that the connection type is an ATAPI internal connector.

### -field AcxConnTypeRCA

Indicates that the connection type is an RCA jack.

### -field AcxConnTypeOptical

Indicates that the connection type is an optical audio jack.

### -field AcxConnTypeOtherDigital

Indicates that the connection type is some other type of digital audio jack not specifically defined by this enum.

### -field AcxConnTypeOtherAnalog

Indicates that the connection type is some other type of analog audio jack not specifically defined by this enum.

### -field AcxConnTypeMultichannelAnalogDIN

Indicates that the connection type is a multichannel analog DIN connector.

### -field AcxConnTypeXlrProfessional

Indicates that the connection type is an XLR jack.

### -field AcxConnTypeRJ11Modem

Indicates that the connection type is an RJ11 modem jack.

### -field AcxConnTypeCombination

Indicates that the connection type is a combination jack.

## -remarks

## -see-also

READY2GO
