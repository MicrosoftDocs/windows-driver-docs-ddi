---
UID: NF:ks.KsReleaseCachedMdl
title: KsReleaseCachedMdl function (ks.h)
description: The KsReleaseCachedMdl function is used to release the MDL acquired by the KsAcquireCachedMdl call.
old-location: stream\ksreleasecachedmdl.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsReleaseCachedMdl function"]
ms.keywords: KsReleaseCachedMdl, KsReleaseCachedMdl function [Streaming Media Devices], ks/KsReleaseCachedMdl, stream.ksreleasecachedmdl
req.header: ks.h
req.include-header: 
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsReleaseCachedMdl
 - ks/KsReleaseCachedMdl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ks.lib
 - ks.dll
api_name:
 - KsReleaseCachedMdl
---

# KsReleaseCachedMdl function


## -description

The <b>KsReleaseCachedMdl</b> function is used to release the MDL acquired by the <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksacquirecachedmdl">KsAcquireCachedMdl</a> call.

## -parameters

### -param Guid [in]


The GUID extracted from the <b>MFSampleExtension_MDLCacheCookie</b> attribute item of the <b>IMFSample</b> passed by the pipeline.

### -param MdlAddr [in]


MDL address retrieved in the <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksacquirecachedmdl">KsAcquireCachedMdl</a> call. This should not be touched after the <b>KsReleaseCachedMdl</b> call.

### -param ReleaseContext [in]


The context passed as an output in the <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksacquirecachedmdl">KsAcquireCachedMdl</a> call.

## -returns

Returns <b>STATUS_SUCCESS</b> for success conditions.
