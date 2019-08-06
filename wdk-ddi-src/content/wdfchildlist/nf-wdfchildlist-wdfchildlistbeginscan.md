---
UID: NF:wdfchildlist.WdfChildListBeginScan
title: WdfChildListBeginScan function (wdfchildlist.h)
description: The WdfChildListBeginScan method prepares a specified list of child devices so the driver can update the information in the list.
old-location: wdf\wdfchildlistbeginscan.htm
tech.root: wdf
ms.assetid: 08951cde-d9d2-4de6-bb63-7c3e7cf1f92f
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectChildListRef_b503df87-d0b1-472d-9981-4896fe81f7d8.xml, WdfChildListBeginScan, WdfChildListBeginScan method, kmdf.wdfchildlistbeginscan, wdf.wdfchildlistbeginscan, wdfchildlist/WdfChildListBeginScan
ms.topic: function
f1_keywords:
 - "wdfchildlist/WdfChildListBeginScan"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfChildListBeginScan
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfChildListBeginScan function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfChildListBeginScan</b> method prepares a specified list of child devices so the driver can update the information in the list.


## -parameters




### -param ChildList [in]

A handle to a framework child list object.


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.





## -remarks



The <b>WdfChildListBeginScan</b> method marks all of the child devices in the list as missing. 

After calling <b>WdfChildListBeginScan</b>, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent">WdfChildListAddOrUpdateChildDescriptionAsPresent</a> repeatedly, or call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistupdateallchilddescriptionsaspresent">WdfChildListUpdateAllChildDescriptionsAsPresent</a>, to report all of the child devices that are currently attached to the parent device. 

After the driver has finished updating the child list, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistendscan">WdfChildListEndScan</a>. This call delivers the updated child list to the Plug and Play (PnP) manager. Subsequently, the framework will call the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_create_device">EvtChildListCreateDevice</a> callback function for each device that the driver reported.

For more information about child lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

For a code example that uses <b>WdfChildListBeginScan</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginiteration">WdfChildListBeginIteration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistendscan">WdfChildListEndScan</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistupdateallchilddescriptionsaspresent">WdfChildListUpdateAllChildDescriptionsAsPresent</a>
 

 

