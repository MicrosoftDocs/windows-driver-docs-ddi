---
UID: NS:wdfchildlist._WDF_CHILD_LIST_ITERATOR
title: _WDF_CHILD_LIST_ITERATOR (wdfchildlist.h)
description: The WDF_CHILD_LIST_ITERATOR structure identifies the type of child devices that the framework will retrieve when a driver calls WdfChildListRetrieveNextDevice.
old-location: wdf\wdf_child_list_iterator.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_CHILD_LIST_ITERATOR structure"]
ms.keywords: "*PWDF_CHILD_LIST_ITERATOR, DFDeviceObjectChildListRef_5a77ee51-8e18-4e86-afd0-8add561dab4d.xml, PWDF_CHILD_LIST_ITERATOR, PWDF_CHILD_LIST_ITERATOR structure pointer, WDF_CHILD_LIST_ITERATOR, WDF_CHILD_LIST_ITERATOR structure, _WDF_CHILD_LIST_ITERATOR, kmdf.wdf_child_list_iterator, wdf.wdf_child_list_iterator, wdfchildlist/PWDF_CHILD_LIST_ITERATOR, wdfchildlist/WDF_CHILD_LIST_ITERATOR"
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: 
targetos: Windows
req.typenames: WDF_CHILD_LIST_ITERATOR, *PWDF_CHILD_LIST_ITERATOR
f1_keywords:
 - _WDF_CHILD_LIST_ITERATOR
 - wdfchildlist/_WDF_CHILD_LIST_ITERATOR
 - PWDF_CHILD_LIST_ITERATOR
 - wdfchildlist/PWDF_CHILD_LIST_ITERATOR
 - WDF_CHILD_LIST_ITERATOR
 - wdfchildlist/WDF_CHILD_LIST_ITERATOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfchildlist.h
api_name:
 - _WDF_CHILD_LIST_ITERATOR
 - PWDF_CHILD_LIST_ITERATOR
 - WDF_CHILD_LIST_ITERATOR
---

# _WDF_CHILD_LIST_ITERATOR structure


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_CHILD_LIST_ITERATOR</b> structure identifies the type of child devices that the framework will retrieve when a driver calls <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a>.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Flags

One or more flags that are defined by the <a href="/windows-hardware/drivers/ddi/wdfchildlist/ne-wdfchildlist-_wdf_retrieve_child_flags">WDF_RETRIEVE_CHILD_FLAGS</a> enumeration.

### -field Reserved

Reserved for internal use only.

## -remarks

The driver must initialize the <b>WDF_CHILD_LIST_ITERATOR</b> structure by calling <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdf_child_list_iterator_init">WDF_CHILD_LIST_ITERATOR_INIT</a>.

The WDF_CHILD_LIST_ITERATOR structure is used as input to the <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginiteration">WdfChildListBeginIteration</a>,<a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a> ,and <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistenditeration">WdfChildListEndIteration</a> methods. The driver must set the <b>Flags</b> member before calling <b>WdfChildListBeginIteration</b>. After calling <b>WdfChildListBeginIteration</b>, the driver must not modify the structure's contents until after calling <b>WdfChildListEndIteration</b>.

For more information about child lists, see <a href="/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdf_child_list_iterator_init">WDF_CHILD_LIST_ITERATOR_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/ne-wdfchildlist-_wdf_retrieve_child_flags">WDF_RETRIEVE_CHILD_FLAGS</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginiteration">WdfChildListBeginIteration</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistenditeration">WdfChildListEndIteration</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a>

