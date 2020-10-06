---
UID: NS:bdasup._BDA_FILTER_TEMPLATE
title: _BDA_FILTER_TEMPLATE (bdasup.h)
description: The BDA_FILTER_TEMPLATE structure describes the template topology for a BDA filter.
old-location: stream\bda_filter_template.htm
tech.root: stream
ms.assetid: 93078225-3487-46db-b13e-e2013be86d97
ms.date: 04/23/2018
keywords: ["BDA_FILTER_TEMPLATE structure"]
ms.keywords: "*PBDA_FILTER_TEMPLATE, BDA_FILTER_TEMPLATE, BDA_FILTER_TEMPLATE structure [Streaming Media Devices], PBDA_FILTER_TEMPLATE, PBDA_FILTER_TEMPLATE structure pointer [Streaming Media Devices], _BDA_FILTER_TEMPLATE, bdaref_cf65795d-632d-4c79-9136-95c256ae8b35.xml, bdasup/BDA_FILTER_TEMPLATE, bdasup/PBDA_FILTER_TEMPLATE, stream.bda_filter_template"
req.header: bdasup.h
req.include-header: Bdasup.h
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
req.typenames: BDA_FILTER_TEMPLATE, *PBDA_FILTER_TEMPLATE
f1_keywords:
 - _BDA_FILTER_TEMPLATE
 - bdasup/_BDA_FILTER_TEMPLATE
 - PBDA_FILTER_TEMPLATE
 - bdasup/PBDA_FILTER_TEMPLATE
 - BDA_FILTER_TEMPLATE
 - bdasup/BDA_FILTER_TEMPLATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bdasup.h
api_name:
 - BDA_FILTER_TEMPLATE
---

# _BDA_FILTER_TEMPLATE structure


## -description

The BDA_FILTER_TEMPLATE structure describes the template topology for a BDA filter.

## -struct-fields

### -field pFilterDescriptor

Points to a KSFILTER_DESCRIPTOR structure that describes a template for a filter for the BDA device.

### -field ulcPinPairs

Number of pairs of pins in the <b>pPinPairs</b> array.

### -field pPinPairs

Array of BDA_PIN_PAIRING structures that describe the topology between a pair of the filter's input and output pins.

## -see-also

<a href="/windows-hardware/drivers/ddi/bdasup/ns-bdasup-_bda_pin_pairing">BDA_PIN_PAIRING</a>



<a href="/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacreatefilterfactory">BdaCreateFilterFactory</a>



<a href="/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdainitfilter">BdaInitFilter</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a>