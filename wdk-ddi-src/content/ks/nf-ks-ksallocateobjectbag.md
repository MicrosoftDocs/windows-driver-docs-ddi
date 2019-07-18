---
UID: NF:ks.KsAllocateObjectBag
title: KsAllocateObjectBag function (ks.h)
description: The KsAllocateObjectBag function creates an object bag and associates it with a KSDEVICE.
old-location: stream\ksallocateobjectbag.htm
tech.root: stream
ms.assetid: 2fc5689f-e1d6-481d-b137-301f10b386e8
ms.date: 04/23/2018
ms.keywords: KsAllocateObjectBag, KsAllocateObjectBag function [Streaming Media Devices], avfunc_a76be7a0-6dfa-4428-8317-4a8df31dec6e.xml, ks/KsAllocateObjectBag, stream.ksallocateobjectbag
ms.topic: function
f1_keywords:
 - "ks/KsAllocateObjectBag"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsAllocateObjectBag
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsAllocateObjectBag function


## -description


The<b> KsAllocateObjectBag</b> function creates an object bag and associates it with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksdevice">KSDEVICE</a>.


## -parameters




### -param Device [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksdevice">KSDEVICE</a> representing the device object associated with the newly created object bag.


### -param ObjectBag [out]

A pointer to a KSOBJECT_BAG (the KSOBJECT_BAG structure is equivalent to type PVOID) where the newly allocated object bag is deposited.


## -returns



Returns STATUS_SUCCESS if a new object bag is created. If a new object bag is not allocated, it returns STATUS_INSUFFICIENT_RESOURCES.




## -remarks



An allocated object bag is not deleted automatically. The minidriver calling <b>KsAllocateObjectBag</b> is responsible for deletion of the object bag. The easiest way to do this is by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksfreeobjectbag">KsFreeObjectBag</a>. Alternatively, if the minidriver has the addresses of the items in the bag, the minidriver can delete them individually by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksremoveitemfromobjectbag">KsRemoveItemFromObjectBag</a>.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/object-bags">Object Bags</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksadditemtoobjectbag">KsAddItemToObjectBag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kscopyobjectbagitems">KsCopyObjectBagItems</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksdiscard">KsDiscard</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksfreeobjectbag">KsFreeObjectBag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksremoveitemfromobjectbag">KsRemoveItemFromObjectBag</a>
 

 

