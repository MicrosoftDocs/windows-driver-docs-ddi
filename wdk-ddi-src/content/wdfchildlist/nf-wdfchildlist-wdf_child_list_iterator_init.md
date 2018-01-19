---
UID: NF:wdfchildlist.WDF_CHILD_LIST_ITERATOR_INIT
title: WDF_CHILD_LIST_ITERATOR_INIT function
author: windows-driver-content
description: The WDF_CHILD_LIST_ITERATOR_INIT function initializes a WDF_CHILD_LIST_ITERATOR structure.
old-location: wdf\wdf_child_list_iterator_init.htm
old-project: wdf
ms.assetid: e06a377a-e68a-4773-9f7f-b1c47010029c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_CHILD_LIST_ITERATOR_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WDF_CHILD_LIST_ITERATOR_INIT
req.alt-loc: Wdfchildlist.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---

# WDF_CHILD_LIST_ITERATOR_INIT function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_CHILD_LIST_ITERATOR_INIT</b> function initializes a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a> structure.



## -syntax

````
VOID WDF_CHILD_LIST_ITERATOR_INIT(
  _Out_ PWDF_CHILD_LIST_ITERATOR Iterator,
  _In_  ULONG                    Flags
);
````


## -parameters

### -param Iterator [out]

A pointer to a driver-supplied <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a> structure.


### -param Flags [in]

A <a href="..\wdfchildlist\ne-wdfchildlist-_wdf_retrieve_child_flags.md">WDF_RETRIEVE_CHILD_FLAGS</a>-typed flag value.


## -returns
None

For a code example that uses <b>WDF_CHILD_LIST_ITERATOR_INIT</b>, see <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a>.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a>
</dt>
<dt>
<a href="..\wdfchildlist\ne-wdfchildlist-_wdf_retrieve_child_flags.md">WDF_RETRIEVE_CHILD_FLAGS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_CHILD_LIST_ITERATOR_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

