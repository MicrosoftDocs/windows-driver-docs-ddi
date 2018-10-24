---
UID: NS:pointofservicecommontypes._BarcodeSymbologyAttributesData
title: "_BarcodeSymbologyAttributesData"
author: windows-driver-content
description: The BarcodeSymbologyAttributesData structure contains the attribute information for a barcode symbology.
old-location: pos\barcodesymbologyattributesdata.htm
tech.root: pos
ms.assetid: 0682B3AA-13F5-4686-AD78-D45DA85398B7
ms.date: 02/23/2018
ms.keywords: BarcodeSymbologyAttributesData, BarcodeSymbologyAttributesData structure, _BarcodeSymbologyAttributesData, pointofservicecommontypes/BarcodeSymbologyAttributesData, pos.barcodesymbologyattributesdata
ms.topic: struct
req.header: pointofservicecommontypes.h
req.include-header: 
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
-	pointofservicecommontypes.h
api_name:
-	BarcodeSymbologyAttributesData
product:
- Windows
targetos: Windows
req.typenames: BarcodeSymbologyAttributesData
---

# _BarcodeSymbologyAttributesData structure


## -description


The <b>BarcodeSymbologyAttributesData</b> structure contains the attribute information  for a barcode symbology.


## -struct-fields




### -field Symbology

The barcode symbology  to set or get attributes to or from.

For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757474">BarcodeSymbology</a> enumeration topic.


### -field IsCheckDigitValidationSupported

Indicates whether the barcode scanner supports check digit of the symbology. Non-zero if supported.


### -field IsCheckDigitValidationEnabled

Indicates whether the target barcodes are expected to contain a check digit.

Some barcodes may have the last digit as a validation digit to ensure  decoding accuracy.  Barcode scanners may choose to support the feature or not. Non-zero if enabled.


### -field IsCheckDigitTransmissionSupported

Indicates whether the barcode scanner supports check digit transmission. Non-zero if supported.


### -field IsCheckDigitTransmissionEnabled

Indicates whether the check digit is transmitted along with the decoded data. Non-zero if enabled.


### -field IsDecodeLengthSupported

Indicates whether the barcode scanner supports setting decode length for the symbology.

For example, the API can be used to set to read barcodes of decode length between 2 and 8.  This helps with filtering the target barcodes. Non-zero if supported.


### -field DecodeLengthType

 The decode length type, which can be set to support a range, two discrete values, or be set to any length.
 For more information, see the <a href="https://msdn.microsoft.com/155D1C71-7935-4512-8AA2-0EB167FCBF5E">BarcodeSymbologyDecodeLengthType</a>.


### -field DecodeLength1

The first  value in a range, or the  first  discrete value.


### -field DecodeLength2

The last value in a range, or a second discrete value.

