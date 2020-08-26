---
UID: NC:wdfchildlist.EVT_WDF_CHILD_LIST_SCAN_FOR_CHILDREN
title: EVT_WDF_CHILD_LIST_SCAN_FOR_CHILDREN (wdfchildlist.h)
description: A driver's EvtChildListScanForChildren event callback function must report all of the child devices that are present.
old-location: wdf\evtchildlistscanforchildren.htm
tech.root: wdf
ms.assetid: 57b06ecd-fc8c-4653-bb78-2bc6ecde6d63
ms.date: 02/26/2018
keywords: ["EVT_WDF_CHILD_LIST_SCAN_FOR_CHILDREN callback function"]
ms.keywords: DFDeviceObjectChildListRef_fa95ef9d-6bb7-4eb0-8535-06853fa1759c.xml, EVT_WDF_CHILD_LIST_SCAN_FOR_CHILDREN, EVT_WDF_CHILD_LIST_SCAN_FOR_CHILDREN callback, EvtChildListScanForChildren, EvtChildListScanForChildren callback function, kmdf.evtchildlistscanforchildren, wdf.evtchildlistscanforchildren, wdfchildlist/EvtChildListScanForChildren
f1_keywords:
 - "wdfchildlist/EvtChildListScanForChildren"
 - "EvtChildListScanForChildren"
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- WdfChildlist.h
api_name:
- EvtChildListScanForChildren
targetos: Windows
req.typenames: 
---

# EVT_WDF_CHILD_LIST_SCAN_FOR_CHILDREN callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtChildListScanForChildren</i> event callback function must report all of the child devices that are present. 


## -parameters




### -param ChildList 
[in]
A handle to a framework child list object.


## -remarks



If a bus driver is using <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListScanForChildren</i> callback function by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>.

If a driver provides an <i>EvtChildListScanForChildren</i> callback function, the framework calls it each time the parent device enters its working (D0) state. (For more information about when this callback function is called, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.)

The driver must report all of its child devices by doing the following:

<ol>
<li>
Calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginscan">WdfChildListBeginScan</a>, which marks all previously reported child devices as missing. 

</li>
<li>
Detecting child devices and calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent">WdfChildListAddOrUpdateChildDescriptionAsPresent</a> for each detected device.

</li>
<li>
Calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistendscan">WdfChildListEndScan</a>, which informs the PnP manager of the reported child devices. 

</li>
</ol>
For more information about dynamic enumeration, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.

The <i>EvtChildListScanForChildren</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginscan">WdfChildListBeginScan</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistendscan">WdfChildListEndScan</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a>
 

 

