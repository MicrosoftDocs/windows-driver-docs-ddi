---
UID: NF:wdfchildlist.WdfChildListBeginIteration
title: WdfChildListBeginIteration function
author: windows-driver-content
description: The WdfChildListBeginIteration method prepares the framework for retrieving items from a specified child list.
old-location: wdf\wdfchildlistbeginiteration.htm
old-project: wdf
ms.assetid: b81dbad8-0e03-4183-a7b3-32c75a656575
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFDeviceObjectChildListRef_98150ed0-3144-4fda-96ca-41573d3013bf.xml, WdfChildListBeginIteration, WdfChildListBeginIteration method, kmdf.wdfchildlistbeginiteration, wdf.wdfchildlistbeginiteration, wdfchildlist/WdfChildListBeginIteration
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfChildListBeginIteration
product: Windows
targetos: Windows
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---

# WdfChildListBeginIteration function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListBeginIteration</b> method prepares the framework for retrieving items from a specified child list.


## -syntax


````
VOID WdfChildListBeginIteration(
  _In_ WDFCHILDLIST             ChildList,
  _In_ PWDF_CHILD_LIST_ITERATOR Iterator
);
````


## -parameters




### -param ChildList [in]

A handle to a framework child list object.


### -param Iterator [in]

A pointer to a caller-allocated <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a> structure that indicates the type of child devices to be retrieved.


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



After calling <b>WdfChildListBeginIteration</b>, the driver can repeatedly call <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a> to obtain information about each child device in the child list. 

After the driver has finished calling <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a>, it must call <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistenditeration.md">WdfChildListEndIteration</a>.

If the driver makes changes to the child list after calling <b>WdfChildListBeginIteration</b>, the framework stores all of the changes and notifies the Plug and Play (PnP) manager of the changes when the driver calls <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistenditeration.md">WdfChildListEndIteration</a>.

The driver can nest calls to <b>WdfChildListBeginIteration</b> and <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistenditeration.md">WdfChildListEndIteration</a>. If the driver nests calls to these methods, the framework stores all of the changes until the last call to <b>WdfChildListEndIteration</b>.

For more information about child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

For a code example that uses <b>WdfChildListBeginIteration</b>, see <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a>.

<div class="code"></div>



## -see-also

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_identification_description_header_init.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginscan.md">WdfChildListBeginScan</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistenditeration.md">WdfChildListEndIteration</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_list_iterator_init.md">WDF_CHILD_LIST_ITERATOR_INIT</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistrequestchildeject.md">WdfChildListRequestChildEject</a>



<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfChildListBeginIteration method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

