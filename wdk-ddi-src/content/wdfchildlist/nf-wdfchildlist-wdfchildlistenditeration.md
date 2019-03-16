---
UID: NF:wdfchildlist.WdfChildListEndIteration
title: WdfChildListEndIteration function (wdfchildlist.h)
description: The WdfChildListEndIteration method processes modifications to a specified child list.
old-location: wdf\wdfchildlistenditeration.htm
tech.root: wdf
ms.assetid: f8dc1d77-d0c5-4112-939d-221955012de1
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectChildListRef_24a52e50-851e-456f-b111-0b794e76acfb.xml, WdfChildListEndIteration, WdfChildListEndIteration method, kmdf.wdfchildlistenditeration, wdf.wdfchildlistenditeration, wdfchildlist/WdfChildListEndIteration
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfChildListEndIteration function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfChildListEndIteration</b> method processes modifications to a specified child list. 


## -parameters




### -param ChildList [in]

The same handle to a framework child-list object that the driver previously specified to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545601">WdfChildListBeginIteration</a>.


### -param Iterator [in]

A pointer to the same caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff551230">WDF_CHILD_LIST_ITERATOR</a> structure that the driver previously supplied to <b>WdfChildListEndIteration</b>.


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.





## -remarks



If the driver has made multiple calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545601">WdfChildListBeginIteration</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545608">WdfChildListBeginScan</a>, the framework does not process modifications to the child list until the driver has made a corresponding number of calls to <b>WdfChildListEndIteration</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff545626">WdfChildListEndScan</a>.

For more information about child lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

For a code example that uses <b>WdfChildListEndIteration</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551230">WDF_CHILD_LIST_ITERATOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545601">WdfChildListBeginIteration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545608">WdfChildListBeginScan</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545626">WdfChildListEndScan</a>
 

 

