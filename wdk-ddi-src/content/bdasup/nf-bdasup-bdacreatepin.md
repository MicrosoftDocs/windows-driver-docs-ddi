---
UID: NF:bdasup.BdaCreatePin
title: BdaCreatePin function (bdasup.h)
description: The BdaCreatePin function creates a new pin in the specified filter.
old-location: stream\bdacreatepin.htm
tech.root: stream
ms.assetid: ac69fdaa-f1e3-4487-93e1-f900f73be2fe
ms.date: 04/23/2018
keywords: ["BdaCreatePin function"]
ms.keywords: BdaCreatePin, BdaCreatePin function [Streaming Media Devices], bdaref_e84fba91-044c-40f3-9364-ede0bbabda48.xml, bdasup/BdaCreatePin, stream.bdacreatepin
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems.
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
req.lib: Bdasup.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - BdaCreatePin
 - bdasup/BdaCreatePin
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaCreatePin
---

# BdaCreatePin function


## -description

The <b>BdaCreatePin</b> function creates a new pin in the specified filter.

## -parameters

### -param pKSFilter 

[in]
Points to the filter in which to create a pin.

### -param ulPinType 

[in]
Specifies the type of pin to create. The BDA minidriver must define a list of pin types for each filter that it supports.

### -param pulPinId 

[out, optional]
Points to a variable that receives the identifier for the created pin.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the <a href="/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdamethodcreatepin">BdaMethodCreatePin</a> function when the network provider dynamically creates a pin using the <a href="/windows-hardware/drivers/stream/ksmethod-bda-create-pin-factory">KSMETHOD_BDA_CREATE_PIN_FACTORY</a> request of the <a href="/windows-hardware/drivers/stream/ksmethodsetid-bdadeviceconfiguration">KSMETHODSETID_BdaDeviceConfiguration</a> method set. If a BDA minidriver must create a pin without relying on the network provider, the BDA minidriver should call the <b>BdaCreatePin</b> function directly.

.

## -see-also

<a href="/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdadeletepin">BdaDeletePin</a>



<a href="/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdamethodcreatepin">BdaMethodCreatePin</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a>



<a href="/windows-hardware/drivers/stream/ksmethodsetid-bdadeviceconfiguration">KSMETHODSETID_BdaDeviceConfiguration</a>



<a href="/windows-hardware/drivers/stream/ksmethod-bda-create-pin-factory">KSMETHOD_BDA_CREATE_PIN_FACTORY</a>