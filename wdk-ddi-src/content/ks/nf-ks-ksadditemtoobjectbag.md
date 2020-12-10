---
UID: NF:ks.KsAddItemToObjectBag
title: KsAddItemToObjectBag function (ks.h)
description: The KsAddItemToObjectBag function adds an object or block of memory to the given object bag.
old-location: stream\ksadditemtoobjectbag.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsAddItemToObjectBag function"]
ms.keywords: KsAddItemToObjectBag, KsAddItemToObjectBag function [Streaming Media Devices], avfunc_c7496331-05a5-4336-9c62-144e2db6e218.xml, ks/KsAddItemToObjectBag, stream.ksadditemtoobjectbag
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
 - KsAddItemToObjectBag
 - ks/KsAddItemToObjectBag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsAddItemToObjectBag
---

# KsAddItemToObjectBag function


## -description

The **KsAddItemToObjectBag** function adds an object or block of memory to the given object bag.

## -parameters

### -param ObjectBag 

[in]
The KSOBJECT_BAG (equivalent to type PVOID) to which to add the requested item. Every AVStream object (for example, [KSFILTER](./ns-ks-_ksfilter.md) and [KSPIN](./ns-ks-_kspin.md)) contains a member called *Bag*. Pass that member in this parameter.

### -param Item 

[in]
A pointer to the item to add to the object bag.

### -param Free 

[in, optional]
A function that is called when the item is removed from the object bag or when the object bag is deleted. This function typically is used to free any dynamic memory associated with *Item*. The function should be prototyped as follows:

```cpp
void Free (IN PVOID Data);
```

If the caller does not specify this optional parameter, *Item* is freed with [ExFreePool](../ntddk/nf-ntddk-exfreepool.md) when removed from the object bag or when the object bag is deleted.

## -returns

Either returns STATUS_SUCCESS indicating that the addition went normally or STATUS_INSUFFICIENT_RESOURCES indicating that there are insufficient system resources for the operation to proceed.

## -remarks

Before calling **KsAddItemToObjectBag**, the minidriver must acquire the mutex associated with the specific object bag. If *ObjectBag* is a member of a [KSDEVICE](./ns-ks-_ksdevice.md) or [KSFILTERFACTORY](./ns-ks-_ksfilterfactory.md), acquire the device mutex. If the bag is a member of a [KSFILTER](./ns-ks-_ksfilter.md), acquire the filter control mutex. If the bag is a member of a [KSPIN](./ns-ks-_kspin.md) object, acquire the parent KSFILTER's filter control mutex.

For more information, see [Object Bags](/windows-hardware/drivers/stream/object-bags) and [Mutexes in AVStream](/windows-hardware/drivers/stream/mutexes-in-avstream).

## -see-also

[ExFreePool](../ntddk/nf-ntddk-exfreepool.md)

[KsAllocateObjectBag](./nf-ks-ksallocateobjectbag.md)

[KsCopyObjectBagItems](./nf-ks-kscopyobjectbagitems.md)

[KsDiscard](./nf-ks-ksdiscard.md)

[KsFreeObjectBag](./nf-ks-ksfreeobjectbag.md)

[KsRemoveItemFromObjectBag](./nf-ks-ksremoveitemfromobjectbag.md)

[_KsEdit](./nf-ks-_ksedit.md)
