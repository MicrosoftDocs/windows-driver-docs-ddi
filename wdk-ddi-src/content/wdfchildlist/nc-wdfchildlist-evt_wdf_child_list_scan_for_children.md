---
UID: NC:wdfchildlist.EVT_WDF_CHILD_LIST_SCAN_FOR_CHILDREN
title: EVT_WDF_CHILD_LIST_SCAN_FOR_CHILDREN
author: windows-driver-content
description: A driver's EvtChildListScanForChildren event callback function must report all of the child devices that are present.
old-location: wdf\evtchildlistscanforchildren.htm
old-project: wdf
ms.assetid: 57b06ecd-fc8c-4653-bb78-2bc6ecde6d63
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtchildlistscanforchildren, EvtChildListScanForChildren callback function, EvtChildListScanForChildren, EVT_WDF_CHILD_LIST_SCAN_FOR_CHILDREN, EVT_WDF_CHILD_LIST_SCAN_FOR_CHILDREN, wdfchildlist/EvtChildListScanForChildren, DFDeviceObjectChildListRef_fa95ef9d-6bb7-4eb0-8535-06853fa1759c.xml, kmdf.evtchildlistscanforchildren
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	WdfChildlist.h
apiname:
-	EvtChildListScanForChildren
product: Windows
targetos: Windows
req.typenames: "*PWDBGEXTS_THREAD_OS_INFO, WDBGEXTS_THREAD_OS_INFO"
req.product: Windows 10 or later.
---

# EVT_WDF_CHILD_LIST_SCAN_FOR_CHILDREN callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtChildListScanForChildren</i> event callback function must report all of the child devices that are present. 


## -prototype


````
EVT_WDF_CHILD_LIST_SCAN_FOR_CHILDREN EvtChildListScanForChildren;

VOID EvtChildListScanForChildren(
  _In_ WDFCHILDLIST ChildList
)
{ ... }
````


## -parameters




### -param ChildList [in]

A handle to a framework child list object.


## -returns


None



## -remarks


If a bus driver is using <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListScanForChildren</i> callback function by calling <a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a> or <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistcreate.md">WdfChildListCreate</a>.

If a driver provides an <i>EvtChildListScanForChildren</i> callback function, the framework calls it each time the parent device enters its working (D0) state. (For more information about when this callback function is called, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.)

The driver must report all of its child devices by doing the following:
<ol>
<li>
Calling <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginscan.md">WdfChildListBeginScan</a>, which marks all previously reported child devices as missing. 

</li>
<li>
Detecting child devices and calling <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent.md">WdfChildListAddOrUpdateChildDescriptionAsPresent</a> for each detected device.

</li>
<li>
Calling <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistendscan.md">WdfChildListEndScan</a>, which informs the PnP manager of the reported child devices. 

</li>
</ol>For more information about dynamic enumeration, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.

The <i>EvtChildListScanForChildren</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.



## -see-also

<a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a>

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginscan.md">WdfChildListBeginScan</a>

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistcreate.md">WdfChildListCreate</a>

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistendscan.md">WdfChildListEndScan</a>

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent.md">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_CHILD_LIST_SCAN_FOR_CHILDREN callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

