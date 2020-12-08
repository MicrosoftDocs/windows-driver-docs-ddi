---
UID: NF:ks.KsRemoveItemFromObjectBag
title: KsRemoveItemFromObjectBag function (ks.h)
description: The KsRemoveItemFromObjectBag function removes an item from an object bag.
old-location: stream\ksremoveitemfromobjectbag.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsRemoveItemFromObjectBag function"]
ms.keywords: KsRemoveItemFromObjectBag, KsRemoveItemFromObjectBag function [Streaming Media Devices], avfunc_dbc6f0e3-7e24-4147-99d2-28e64a6a1ff9.xml, ks/KsRemoveItemFromObjectBag, stream.ksremoveitemfromobjectbag
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsRemoveItemFromObjectBag
 - ks/KsRemoveItemFromObjectBag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsRemoveItemFromObjectBag
---

# KsRemoveItemFromObjectBag function


## -description

The<b> KsRemoveItemFromObjectBag </b>function removes an item from an object bag.

## -parameters

### -param ObjectBag 

[in]
This parameter specifies the KSOBJECT_BAG (equivalent to type PVOID) from which to remove <i>Item</i>.

### -param Item 

[in]
A pointer to the item to remove from the requested object bag. Note that <i>Item</i> is removed from the requested object bag only. It is not removed from any other object bags that it may be in.

### -param Free 

[in]
This parameter specifies whether <i>Item</i> should be freed once it has been removed from the specified object bag. Only set <i>Free</i> to <b>TRUE</b> if <i>Item</i> is not contained in any other object bag.

## -returns

Returns the number of references on <i>Item</i>. A return value of zero indicates that <i>Item</i> was not in <i>ObjectBag</i> at call-time.

A return value of one indicates that <i>Item</i> was successfully removed from <i>ObjectBag</i> and that it was not in any other object bag. If a free was requested in this case, AVStream frees <i>Item</i> using either <b>ExFreePool</b> or the Free method specified at <b>KsAddItemToObjectBag</b> call-time.



A return value above one indicates that the item is present in another object bag and that there are still references on it. In this case, AVStream removed Item from <i>ObjectBag</i>, but did not free it regardless of the value of <i>Free</i>.

## -remarks

<b>KsRemoveItemFromObjectBag</b> frees <i>Item</i> only if the number of references on this item is zero and a free was requested. 

For more information about object bags, see <a href="/windows-hardware/drivers/stream/object-bags">Object Bags</a>.

Note that the mutex associated with the bag must be held. For more  information, see <a href="/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksadditemtoobjectbag">KsAddItemToObjectBag</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksallocateobjectbag">KsAllocateObjectBag</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kscopyobjectbagitems">KsCopyObjectBagItems</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksdiscard">KsDiscard</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfreeobjectbag">KsFreeObjectBag</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksmergeautomationtables">KsMergeAutomationTables</a>
