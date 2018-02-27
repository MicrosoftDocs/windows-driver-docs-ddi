---
UID: NF:wdfchildlist.WdfChildListUpdateAllChildDescriptionsAsPresent
title: WdfChildListUpdateAllChildDescriptionsAsPresent function
author: windows-driver-content
description: The WdfChildListUpdateAllChildDescriptionsAsPresent method informs the framework that all of the child devices in a specified child list are plugged in and available.
old-location: wdf\wdfchildlistupdateallchilddescriptionsaspresent.htm
old-project: wdf
ms.assetid: 598d2b4f-9b49-480a-9cf8-25661c24483f
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFDeviceObjectChildListRef_55956590-2843-4486-acfb-0e85c01702a0.xml, WdfChildListUpdateAllChildDescriptionsAsPresent, WdfChildListUpdateAllChildDescriptionsAsPresent method, kmdf.wdfchildlistupdateallchilddescriptionsaspresent, wdf.wdfchildlistupdateallchilddescriptionsaspresent, wdfchildlist/WdfChildListUpdateAllChildDescriptionsAsPresent
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
-	WdfChildListUpdateAllChildDescriptionsAsPresent
product: Windows
targetos: Windows
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---

# WdfChildListUpdateAllChildDescriptionsAsPresent function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListUpdateAllChildDescriptionsAsPresent</b> method informs the framework that all of the child devices in a specified child list are plugged in and available.


## -syntax


````
VOID WdfChildListUpdateAllChildDescriptionsAsPresent(
  _In_ WDFCHILDLIST ChildList
);
````


## -parameters




### -param ChildList [in]

A handle to a child list object.


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.





## -remarks



The <b>WdfChildListUpdateAllChildDescriptionsAsPresent</b> method is available in version 1.0 and later versions of KMDF.

For more information about child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

The following code example informs the framework that all of the devices that a device list represents are plugged in and available.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfChildListUpdateAllChildDescriptionsAsPresent(DeviceList);</pre>
</td>
</tr>
</table></span></div>


