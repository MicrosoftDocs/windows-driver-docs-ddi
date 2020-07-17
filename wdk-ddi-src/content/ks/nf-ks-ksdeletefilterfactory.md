---
UID: NF:ks.KsDeleteFilterFactory
title: KsDeleteFilterFactory macro (ks.h)
description: KsDeleteFilterFactory deletes a given filter factory.
old-location: stream\ksdeletefilterfactory.htm
tech.root: stream
ms.assetid: 4d946524-8ad2-45a0-91be-861b30b0c297
ms.date: 04/23/2018
keywords: ["KsDeleteFilterFactory macro"]
ms.keywords: KsDeleteFilterFactory, KsDeleteFilterFactory function [Streaming Media Devices], avfunc_60aeaa09-5563-47ea-a117-4b65a468b058.xml, ks/KsDeleteFilterFactory, stream.ksdeletefilterfactory
f1_keywords:
 - "ks/KsDeleteFilterFactory"
 - "KsDeleteFilterFactory"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ks.h
api_name:
- KsDeleteFilterFactory
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsDeleteFilterFactory macro

## -description

**KsDeleteFilterFactory** deletes a given filter factory.

## -parameters

### -param FilterFactory [in]

A pointer to a [KSFILTERFACTORY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory) structure that represents the filter factory to be deleted.

## -returns

This macro wraps and assumes the return value of [KsFreeObjectCreateItemsByContext](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfreeobjectcreateitemsbycontext), which is NTSTATUS.

## -see-also

[KSFILTERFACTORY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory)

[KsCreateFilterFactory](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kscreatefilterfactory)

[KsFilterFactoryAddCreateItem](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterfactoryaddcreateitem)

[KsFilterFactorySetDeviceClassesState](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterfactorysetdeviceclassesstate)
