---
UID: NF:bdasup.BdaCreateFilterFactory
title: BdaCreateFilterFactory function (bdasup.h)
description: The BdaCreateFilterFactory function adds the specified filter descriptor as a filter factory to the specified device and associates the filter factory with the specified BDA template topology.
old-location: stream\bdacreatefilterfactory.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["BdaCreateFilterFactory function"]
ms.keywords: BdaCreateFilterFactory, BdaCreateFilterFactory function [Streaming Media Devices], bdaref_187ab038-cc22-4f82-a9c9-b326b77fef64.xml, bdasup/BdaCreateFilterFactory, stream.bdacreatefilterfactory
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
 - BdaCreateFilterFactory
 - bdasup/BdaCreateFilterFactory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaCreateFilterFactory
---

# BdaCreateFilterFactory function


## -description

The <b>BdaCreateFilterFactory</b> function adds the specified filter descriptor as a filter factory to the specified device and associates the filter factory with the specified BDA template topology.

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

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the <b>BdaCreateFilterFactory</b> function to add a filter factory with an associated BDA template topology to a device and to register all of the topology's static template structures with the BDA support library (<i>BdaSup.sys</i>). The BDA support library can then handle the following method and property calls: 

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
If a BDA minidriver requires a pointer to the newly created filter factory (<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a>), the minidriver should call the <a href="/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacreatefilterfactoryex">BdaCreateFilterFactoryEx</a> function instead.

## -see-also

<a href="/windows-hardware/drivers/ddi/bdasup/ns-bdasup-_bda_filter_template">BDA_FILTER_TEMPLATE</a>



<a href="/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacreatefilterfactoryex">BdaCreateFilterFactoryEx</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync">KSMETHODSETID_BdaChangeSync</a>



<a href="/windows-hardware/drivers/stream/ksmethodsetid-bdadeviceconfiguration">KSMETHODSETID_BdaDeviceConfiguration</a>



<a href="/windows-hardware/drivers/stream/kspropsetid-bdatopology">KSPROPSETID_BdaTopology</a>
