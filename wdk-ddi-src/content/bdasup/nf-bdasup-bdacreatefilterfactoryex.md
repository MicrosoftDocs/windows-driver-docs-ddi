---
UID: NF:bdasup.BdaCreateFilterFactoryEx
title: BdaCreateFilterFactoryEx function (bdasup.h)
description: The BdaCreateFilterFactoryEx function adds the specified filter descriptor as a filter factory to the specified device and associates the filter factory with the specified BDA template topology.
old-location: stream\bdacreatefilterfactoryex.htm
tech.root: stream
ms.assetid: 105b6a66-5800-4079-af88-f44d01134ff0
ms.date: 04/23/2018
keywords: ["BdaCreateFilterFactoryEx function"]
ms.keywords: BdaCreateFilterFactoryEx, BdaCreateFilterFactoryEx function [Streaming Media Devices], bdaref_9a145859-e899-4180-ac91-63479e4e04c0.xml, bdasup/BdaCreateFilterFactoryEx, stream.bdacreatefilterfactoryex
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
 - BdaCreateFilterFactoryEx
 - bdasup/BdaCreateFilterFactoryEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaCreateFilterFactoryEx
---

# BdaCreateFilterFactoryEx function


## -description

The <b>BdaCreateFilterFactoryEx</b> function adds the specified filter descriptor as a filter factory to the specified device and associates the filter factory with the specified BDA template topology.

## -parameters

### -param pKSDevice 

[in]
Points to the BDA device to which to add the filter factory with associated BDA template topology.

### -param pFilterDescriptor 

[in]
Points to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a> structure that describes a filter for the BDA device. Note that not all of the template pin and node types may be exposed as pin and node factories when the filter is first initialized.

### -param pBdaFilterTemplate 

[in]
Points to a <a href="/windows-hardware/drivers/ddi/bdasup/ns-bdasup-_bda_filter_template">BDA_FILTER_TEMPLATE</a> structure that describes a BDA template topology.

### -param ppKSFilterFactory 

[out, optional]
Points to a buffer that receives a pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a> structure for the newly created filter factory.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the <b>BdaCreateFilterFactoryEx</b> function to add a filter factory with an associated BDA template topology to a device and to register all of the topology's static template structures with the BDA support library (<i>BdaSup.sys</i>). The BDA support library can then handle the following method and property calls: 

<ul>
<li>

<a href="/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync">KSMETHODSETID_BdaChangeSync</a>


</li>
<li>

<a href="/windows-hardware/drivers/stream/ksmethodsetid-bdadeviceconfiguration">KSMETHODSETID_BdaDeviceConfiguration</a>


</li>
<li>

<a href="/windows-hardware/drivers/stream/kspropsetid-bdatopology">KSPROPSETID_BdaTopology</a>


</li>
</ul>
A BDA minidriver calls <b>BdaCreateFilterFactoryEx</b> rather than the <a href="/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacreatefilterfactory">BdaCreateFilterFactory</a> function whenever it requires a pointer to the newly created KSFILTERFACTORY. The <b>BdaCreateFilterFactory</b> function also creates a filter factory but doesn't return it to the caller. The BDA minidriver requires a pointer to the newly created KSFILTERFACTORY if the minidriver must call the <a href="/windows-hardware/drivers/ddi/ks/nf-ks-_ksedit">_KsEdit</a> function to edit KSFILTERFACTORY.

## -see-also

<a href="/windows-hardware/drivers/ddi/bdasup/ns-bdasup-_bda_filter_template">BDA_FILTER_TEMPLATE</a>



<a href="/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacreatefilterfactory">BdaCreateFilterFactory</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync">KSMETHODSETID_BdaChangeSync</a>



<a href="/windows-hardware/drivers/stream/ksmethodsetid-bdadeviceconfiguration">KSMETHODSETID_BdaDeviceConfiguration</a>



<a href="/windows-hardware/drivers/stream/kspropsetid-bdatopology">KSPROPSETID_BdaTopology</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-_ksedit">_KsEdit</a>