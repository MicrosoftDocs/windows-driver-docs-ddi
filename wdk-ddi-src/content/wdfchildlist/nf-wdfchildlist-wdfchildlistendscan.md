---
UID: NF:wdfchildlist.WdfChildListEndScan
title: WdfChildListEndScan function (wdfchildlist.h)
description: The WdfChildListEndScan method processes modifications to a specified child list.
old-location: wdf\wdfchildlistendscan.htm
tech.root: wdf
ms.assetid: 73891793-e59f-4c67-af93-07929d7c7326
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectChildListRef_ffd03c13-6074-4679-bb87-b2c028fc8ded.xml, WdfChildListEndScan, WdfChildListEndScan method, kmdf.wdfchildlistendscan, wdf.wdfchildlistendscan, wdfchildlist/WdfChildListEndScan
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
- WdfChildListEndScan
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfChildListEndScan function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfChildListEndScan</b> method processes modifications to a specified child list. 


## -parameters




### -param ChildList [in]

The same handle to a framework child-list object that the driver previously specified to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginscan">WdfChildListBeginScan</a>.


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.





## -remarks



If the driver has made multiple calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginiteration">WdfChildListBeginIteration</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginscan">WdfChildListBeginScan</a>, the framework does not process modifications to the child list until the driver has made a corresponding number of calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistenditeration">WdfChildListEndIteration</a> and <b>WdfChildListEndScan</b>.

For more information about child lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

For a code example that uses <b>WdfChildListEndScan</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginiteration">WdfChildListBeginIteration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginscan">WdfChildListBeginScan</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistenditeration">WdfChildListEndIteration</a>
 

 

