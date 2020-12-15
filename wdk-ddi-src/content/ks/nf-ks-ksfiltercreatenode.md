---
UID: NF:ks.KsFilterCreateNode
title: KsFilterCreateNode function (ks.h)
description: The KsFilterCreateNode function creates a new topology node on the specified filter.
old-location: stream\ksfiltercreatenode.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsFilterCreateNode function"]
ms.keywords: KsFilterCreateNode, KsFilterCreateNode function [Streaming Media Devices], avfunc_9adc2406-964c-4f26-a155-67f37cceb0b4.xml, ks/KsFilterCreateNode, stream.ksfiltercreatenode
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsFilterCreateNode
 - ks/KsFilterCreateNode
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsFilterCreateNode
---

# KsFilterCreateNode function


## -description

The<b> KsFilterCreateNode</b> function creates a new topology node on the specified filter.

## -parameters

### -param Filter 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure on which to create a new topology node.

### -param NodeDescriptor 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksnode_descriptor">KSNODE_DESCRIPTOR</a> structure that describes the new node.

### -param NodeID 

[out]
A pointer to a ULONG where AVStream places the ID of the new node.

## -returns

<b>KsFilterCreateNode</b>  returns the success or failure of creating the node. The call may fail because of invalid parameters, low memory, or other reasons.

## -remarks

Note that the filter control mutex must be held before calling this function. For more information, see <a href="/windows-hardware/drivers/stream/filter-control-mutex-in-avstream">Filter Control Mutex in AVStream</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltercreatepinfactory">KsFilterCreatePinFactory</a>
