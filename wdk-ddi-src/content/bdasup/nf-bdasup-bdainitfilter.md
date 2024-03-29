---
UID: NF:bdasup.BdaInitFilter
title: BdaInitFilter function (bdasup.h)
description: The BdaInitFilter function initializes the BDA filter context associated with a filter instance.
old-location: stream\bdainitfilter.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["BdaInitFilter function"]
ms.keywords: BdaInitFilter, BdaInitFilter function [Streaming Media Devices], bdaref_9ad4e7ef-1880-4233-83c5-4d066c8f26e5.xml, bdasup/BdaInitFilter, stream.bdainitfilter
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
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
 - BdaInitFilter
 - bdasup/BdaInitFilter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaInitFilter
---

# BdaInitFilter function


## -description

The <b>BdaInitFilter</b> function initializes the BDA filter context associated with a filter instance.

## -parameters

### -param pKSFilter [in]


Points to the filter in which to initialize the BDA filter context.

### -param pBdaFilterTemplate [in]


Points to a <a href="/windows-hardware/drivers/ddi/bdasup/ns-bdasup-_bda_filter_template">BDA_FILTER_TEMPLATE</a> structure that describes the filter template for the BDA device. To determine topology for and configure the initialized filter, the network provider uses information referenced in this BDA_FILTER_TEMPLATE structure.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the <b>BdaInitFilter</b> function to initialize an instance of a filter using a specific BDA filter template and a filter factory that was previously created through a call to the <a href="/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacreatefilterfactory">BdaCreateFilterFactory</a> function. The BDA minidriver can subsequently use this filter instance in calls to other BDA support functions, such as, <a href="/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacreatepin">BdaCreatePin</a>. 

When a BDA minidriver calls <b>BdaInitFilter</b>, the BDA support driver (<i>Bdasup.sys</i>) creates its own BDA filter context. This BDA filter context is hidden from the BDA minidriver. However, when required, the BDA support driver can access this BDA filter context. The BDA support driver adds a pointer to this BDA filter context to the object bag for the associated <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> object. When the associated KSFILTER object is destroyed, AVStream requests that the BDA support driver delete this BDA filter context from the object bag. In this way, the BDA support driver can destroy this BDA filter context without requiring intervention by the BDA minidriver.

## -see-also

<a href="/windows-hardware/drivers/ddi/bdasup/ns-bdasup-_bda_filter_template">BDA_FILTER_TEMPLATE</a>



<a href="/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacreatefilterfactory">BdaCreateFilterFactory</a>



<a href="/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacreatepin">BdaCreatePin</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a>
