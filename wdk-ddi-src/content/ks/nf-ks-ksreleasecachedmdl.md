---
UID: NF:ks.KsReleaseCachedMdl
title: KsReleaseCachedMdl function
author: windows-driver-content
description: The KsReleaseCachedMdl function is used to release the MDL acquired by the KsAcquireCachedMdl call.
old-location: stream\ksreleasecachedmdl.htm
tech.root: stream
ms.assetid: 8EDBD8FF-6417-44C0-87C0-14D71FEFA380
ms.date: 4/23/2018
ms.keywords: KsReleaseCachedMdl, KsReleaseCachedMdl function [Streaming Media Devices], ks/KsReleaseCachedMdl, stream.ksreleasecachedmdl
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ks.lib
-	ks.dll
api_name:
-	KsReleaseCachedMdl
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsReleaseCachedMdl function


## -description


The <b>KsReleaseCachedMdl</b> function is used to release the MDL acquired by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186387">KsAcquireCachedMdl</a> call.


## -parameters




### -param Guid [in]

The GUID extracted from the <b>MFSampleExtension_MDLCacheCookie</b> attribute item of the <b>IMFSample</b> passed by the pipeline.


### -param MdlAddr [in]

MDL address retrieved in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186387">KsAcquireCachedMdl</a> call. This should not be touched after the <b>KsReleaseCachedMdl</b> call.


### -param ReleaseContext [in]

The context passed as an output in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186387">KsAcquireCachedMdl</a> call.


## -returns



Returns <b>STATUS_SUCCESS</b> for success conditions.



