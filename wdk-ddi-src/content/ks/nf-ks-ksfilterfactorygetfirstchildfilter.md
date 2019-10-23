---
UID: NF:ks.KsFilterFactoryGetFirstChildFilter
title: KsFilterFactoryGetFirstChildFilter function (ks.h)
description: The KsFilterFactoryGetFirstChildFilter function returns the first instantiated filter created by FilterFactory.
old-location: stream\ksfilterfactorygetfirstchildfilter.htm
tech.root: stream
ms.assetid: 72eb23aa-4f0e-4ef5-baee-c0735253684e
ms.date: 04/23/2018
ms.keywords: KsFilterFactoryGetFirstChildFilter, KsFilterFactoryGetFirstChildFilter function [Streaming Media Devices], avfunc_1e512072-d270-48d9-8289-feaf8d2bcf35.xml, ks/KsFilterFactoryGetFirstChildFilter, stream.ksfilterfactorygetfirstchildfilter
ms.topic: function
f1_keywords:
 - "ks/KsFilterFactoryGetFirstChildFilter"
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
- ks.h
api_name:
- KsFilterFactoryGetFirstChildFilter
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFilterFactoryGetFirstChildFilter function


## -description


The<b> KsFilterFactoryGetFirstChildFilter</b> function returns the first instantiated filter created by <i>FilterFactory</i>.


## -parameters




### -param FilterFactory [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a> structure for which to find the first instantiated child filter.


## -returns



<b>KsFilterFactoryGetFirstChildFilter</b> returns a pointer to the first instantiated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure created by <i>FilterFactory</i>. If there are no instantiated filters created by <i>FilterFactory</i>, <b>NULL</b> is returned.




## -remarks



This call is an inline function call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetfirstchild">KsGetFirstChild</a>. Note that the object hierarchy is guaranteed to be stable only while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetnextsiblingfilter">KsFilterGetNextSiblingFilter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetfirstchild">KsGetFirstChild</a>
 

 

