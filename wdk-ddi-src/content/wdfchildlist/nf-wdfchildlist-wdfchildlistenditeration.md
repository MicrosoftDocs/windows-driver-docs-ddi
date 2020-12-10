---
UID: NF:wdfchildlist.WdfChildListEndIteration
title: WdfChildListEndIteration function (wdfchildlist.h)
description: The WdfChildListEndIteration method processes modifications to a specified child list.
old-location: wdf\wdfchildlistenditeration.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfChildListEndIteration function"]
ms.keywords: DFDeviceObjectChildListRef_24a52e50-851e-456f-b111-0b794e76acfb.xml, WdfChildListEndIteration, WdfChildListEndIteration method, kmdf.wdfchildlistenditeration, wdf.wdfchildlistenditeration, wdfchildlist/WdfChildListEndIteration
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfChildListEndIteration
 - wdfchildlist/WdfChildListEndIteration
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfChildListEndIteration
---

# WdfChildListEndIteration function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfChildListEndIteration</b> method processes modifications to a specified child list.

## -parameters

### -param ChildList 

[in]
The same handle to a framework child-list object that the driver previously specified to <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginiteration">WdfChildListBeginIteration</a>.

### -param Iterator 

[in]
A pointer to the same caller-allocated <a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_list_iterator">WDF_CHILD_LIST_ITERATOR</a> structure that the driver previously supplied to <b>WdfChildListEndIteration</b>.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.




If the driver has made multiple calls to <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginiteration">WdfChildListBeginIteration</a> or <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginscan">WdfChildListBeginScan</a>, the framework does not process modifications to the child list until the driver has made a corresponding number of calls to <b>WdfChildListEndIteration</b> and <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistendscan">WdfChildListEndScan</a>.

For more information about child lists, see <a href="/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

For a code example that uses <b>WdfChildListEndIteration</b>, see <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_list_iterator">WDF_CHILD_LIST_ITERATOR</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginiteration">WdfChildListBeginIteration</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginscan">WdfChildListBeginScan</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistendscan">WdfChildListEndScan</a>
