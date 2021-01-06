---
UID: NF:ks.KsDeleteFilterFactory
title: KsDeleteFilterFactory macro (ks.h)
description: KsDeleteFilterFactory deletes a given filter factory.
old-location: stream\ksdeletefilterfactory.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsDeleteFilterFactory macro"]
ms.keywords: KsDeleteFilterFactory, KsDeleteFilterFactory function [Streaming Media Devices], avfunc_60aeaa09-5563-47ea-a117-4b65a468b058.xml, ks/KsDeleteFilterFactory, stream.ksdeletefilterfactory
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsDeleteFilterFactory
 - ks/KsDeleteFilterFactory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ks.h
api_name:
 - KsDeleteFilterFactory
---

# KsDeleteFilterFactory macro


## -description

**KsDeleteFilterFactory** deletes a given filter factory.

## -parameters

### -param FilterFactory 

[in]
A pointer to a [KSFILTERFACTORY](./ns-ks-_ksfilterfactory.md) structure that represents the filter factory to be deleted.

## -returns

This macro wraps and assumes the return value of [KsFreeObjectCreateItemsByContext](./nf-ks-ksfreeobjectcreateitemsbycontext.md), which is NTSTATUS.

## -see-also

[KSFILTERFACTORY](./ns-ks-_ksfilterfactory.md)

[KsCreateFilterFactory](./nf-ks-kscreatefilterfactory.md)

[KsFilterFactoryAddCreateItem](./nf-ks-ksfilterfactoryaddcreateitem.md)

[KsFilterFactorySetDeviceClassesState](./nf-ks-ksfilterfactorysetdeviceclassesstate.md)
