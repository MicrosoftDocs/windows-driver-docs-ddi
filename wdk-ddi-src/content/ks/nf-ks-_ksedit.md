---
UID: NF:ks._KsEdit
title: "_KsEdit function"
author: windows-driver-content
description: The _KsEdit function guarantees that a given item is dynamically allocated and associated with an AVStream object through the object bag.
old-location: stream\_ksedit.htm
old-project: stream
ms.assetid: 9368846a-b985-40f4-8b02-1bb48431141a
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "_KsEdit, avfunc_1e902412-8322-4155-9fdb-dfc0fa1b6b37.xml, ks/_KsEdit, _KsEdit function [Streaming Media Devices], stream._ksedit"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	_KsEdit
product: Windows
targetos: Windows
req.typenames: 
---

# _KsEdit function


## -description


The <b>_KsEdit</b> function guarantees that a given item is dynamically allocated and associated with an AVStream object through the object bag.


## -syntax


````
NTSTATUS _KsEdit(
  _In_    KSOBJECT_BAG ObjectBag,
  _Inout_ PVOID        *PointerToPointerToItem,
  _In_    ULONG        NewSize,
  _In_    ULONG        OldSize,
  _In_    ULONG        Tag
);
````


## -parameters




### -param ObjectBag [in]

The KSOBJECT_BAG (equivalent to type PVOID) to use in the check. If the item is not contained within the object bag, <b>_KsEdit</b> dynamically allocates sufficient memory for the item, copies the old contents, and places the newly allocated memory in this object bag.


### -param PointerToPointerToItem [in, out]

A pointer to a pointer to the item being edited.


### -param NewSize [in]

The number of bytes to allocate for the item.


### -param OldSize [in]

The number of bytes the item currently takes up.


### -param Tag [in]

Contains the pool tag to use for the allocations. Drivers normally specify the pool tag as a string of up to four characters, delimited by single quotation marks. The string is usually specified in reversed order. The ASCII value of each character in the tag must be between 0 and 127.


## -returns



Returns success or STATUS_INSUFFICIENT_RESOURCES.




## -remarks



Note that <b>KsEdit</b> and <b>KsEditSized</b> are macros created to make <b>_KsEdit</b> easier to use. While <b>_KsEdit</b> allows you to resize an item, <b>KsEdit</b> does not. The macro <b>KsEdit</b> calls <b>_KsEdit</b>, specifying <b>sizeof</b>(**<i>PointerToPointerToItem</i>) as both sizes.

For example, consider a pin that needs to modify its allocator framing on creation. Because the descriptor is statically coded and new pins may use it, the solution is to modify the pin descriptor as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>        KsEdit(Pin, &amp;Pin-&gt;Descriptor, Tag);
        Pin-&gt;Descriptor-&gt;AllocatorFraming = NewAllocatorFraming;</pre>
</td>
</tr>
</table></span></div>
The call to <b>KsEdit</b> guarantees that <i>Pin-&gt;Descriptor </i>is dynamic memory that is associated with <i>Pin</i>. Note that arbitrary modification of descriptors and other AVStream structures can cause undesirable results. Minidrivers should exercise caution when using <b>KsEdit</b> on AVStream structures.

<b>KsEditSized</b> calls <b>_KsEdit</b> with the same parameters it receives, except that <i>Object</i> is replaced by <i>Object-&gt;Bag</i> and the pointer is typecast to PVOID.

Note that when calling <b>_KsEdit</b>, a caller must hold the mutex associated with the bag. For more information, see <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a> and <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>. 



