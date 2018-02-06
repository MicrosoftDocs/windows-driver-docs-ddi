---
UID: NF:ks.KsReleaseCachedMdl
title: KsReleaseCachedMdl function
author: windows-driver-content
description: The KsReleaseCachedMdl function is used to release the MDL acquired by the KsAcquireCachedMdl call.
old-location: stream\ksreleasecachedmdl.htm
old-project: stream
ms.assetid: 8EDBD8FF-6417-44C0-87C0-14D71FEFA380
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ksreleasecachedmdl, KsReleaseCachedMdl function [Streaming Media Devices], KsReleaseCachedMdl, ks/KsReleaseCachedMdl
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ks.lib
-	ks.dll
apiname:
-	KsReleaseCachedMdl
product: Windows
targetos: Windows
req.typenames: 
---

# KsReleaseCachedMdl function


## -description


The <b>KsReleaseCachedMdl</b> function is used to release the MDL acquired by the <a href="..\ks\nf-ks-ksacquirecachedmdl.md">KsAcquireCachedMdl</a> call.


## -syntax


````
void _Must_inspect_result_ _IRQL_requires_max_(PASSIVE_LEVEL) KSDDKAPI NTSTATUS WINAPI KsReleaseCachedMdl(
  _In_ REFGUID Guid,
  _In_ PMDL    MdlAddr,
  _In_ HANDLE  ReleaseContext
);
````


## -parameters




### -param Guid [in]

The GUID extracted from the <b>MFSampleExtension_MDLCacheCookie</b> attribute item of the <b>IMFSample</b> passed by the pipeline.


### -param MdlAddr [in]

MDL address retrieved in the <a href="..\ks\nf-ks-ksacquirecachedmdl.md">KsAcquireCachedMdl</a> call. This should not be touched after the <b>KsReleaseCachedMdl</b> call.


### -param ReleaseContext [in]

The context passed as an output in the <a href="..\ks\nf-ks-ksacquirecachedmdl.md">KsAcquireCachedMdl</a> call.


## -returns


Returns <b>STATUS_SUCCESS</b> for success conditions.


