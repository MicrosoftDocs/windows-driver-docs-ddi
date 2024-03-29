---
UID: NF:ks.KsPinGetCopyRelationships
title: KsPinGetCopyRelationships function (ks.h)
description: The KsPinGetCopyRelationships function returns copy relationship information for a pin that is contained within a pin-centric filter.
old-location: stream\kspingetcopyrelationships.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsPinGetCopyRelationships function"]
ms.keywords: KsPinGetCopyRelationships, KsPinGetCopyRelationships function [Streaming Media Devices], avfunc_d44ce272-9171-4a32-89c6-023d9688fdfd.xml, ks/KsPinGetCopyRelationships, stream.kspingetcopyrelationships
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsPinGetCopyRelationships
 - ks/KsPinGetCopyRelationships
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsPinGetCopyRelationships
---

# KsPinGetCopyRelationships function


## -description

The <b>KsPinGetCopyRelationships</b> function returns copy relationship information for a pin that is contained within a <a href="/windows-hardware/drivers/stream/pin-centric-processing">pin-centric</a> filter.

## -parameters

### -param Pin [in]


A pointer to the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure from which you want to acquire copy information.

### -param CopySource [out]


A pointer to a pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure that is the copy source for <i>Pin</i>. If <i>Pin</i> is the copy source, AVStream sets this parameter to <b>NULL</b>.

### -param DelegateBranch [out]


A pointer to a pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure that is the pin from which <i>Pin</i> receives delegated frames. If <i>Pin</i> is the delegator, AVStream sets this parameter to <b>NULL</b>.

## -remarks

<a href="/windows-hardware/drivers/stream/filter-centric-processing">Filter-centric</a> filters receive similar <i>CopySource</i> and <i>DelegateBranch</i> information when AVStream calls the minidriver's <a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnksfilterprocess">AVStrMiniFilterProcess</a> function with an array of <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksprocesspin_indexentry">KSPROCESSPIN_INDEXENTRY</a> structures.

The only difference is that <b>KsPinGetCopyRelationships</b> returns pointers to PKSPIN rather than pointers to PKSPROCESSPIN. For more information about the <i>CopySource</i> and <i>DelegateBranch</i> parameters, see <a href="/windows-hardware/drivers/stream/avstream-splitters">AVStream Splitters</a>.

All pins operate independently in the context of a pin-centric filter. As a result, a minidriver that calls <b>KsPinGetCopyRelationships</b> is responsible for ensuring that the appropriate synchronization is performed before call time.

To guarantee safety when calling <b>KsPinGetCopyRelationships</b>, either obtain the control mutex (do not use this mechanism in a processing dispatch) or make sure that the pin does not transition below <b>KSSTATE_PAUSE</b> while calling or using the information obtained. For more information about mutexes, see <a href="/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

For more information, see <a href="/windows-hardware/drivers/stream/pin-centric-processing">Pin-Centric Processing</a> and <a href="/windows-hardware/drivers/stream/filter-centric-processing">Filter-Centric Processing</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksprocesspin">KSPROCESSPIN</a>
