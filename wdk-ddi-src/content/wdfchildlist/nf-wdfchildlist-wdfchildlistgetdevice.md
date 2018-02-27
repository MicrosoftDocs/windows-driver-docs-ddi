---
UID: NF:wdfchildlist.WdfChildListGetDevice
title: WdfChildListGetDevice function
author: windows-driver-content
description: The WdfChildListGetDevice method returns a handle to the framework device object that represents the parent device of a specified child list.
old-location: wdf\wdfchildlistgetdevice.htm
old-project: wdf
ms.assetid: 5d51ec82-4891-47f1-8fc1-b20cb611d7fe
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFDeviceObjectChildListRef_3126e6d6-e0d4-4ad1-865e-e7ec36e3c593.xml, WdfChildListGetDevice, WdfChildListGetDevice method, kmdf.wdfchildlistgetdevice, wdf.wdfchildlistgetdevice, wdfchildlist/WdfChildListGetDevice
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
-	WdfChildListGetDevice
product: Windows
targetos: Windows
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---

# WdfChildListGetDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListGetDevice</b> method returns a handle to the framework device object that represents the parent device of a specified child list.


## -syntax


````
WDFDEVICE WdfChildListGetDevice(
  _In_ WDFCHILDLIST ChildList
);
````


## -parameters




### -param ChildList [in]

A handle to a framework child-list object.


## -returns



<b>WdfChildListGetDevice</b> returns a handle to a framework device object.

A system bug check occurs if the driver supplies an invalid object handle.





## -remarks



For more information about child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

The following code example obtains a handle to the device object that represents the parent device of a child list.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFDEVICE parentDevice;

parentDevice = WdfChildListGetDevice(ChildList);</pre>
</td>
</tr>
</table></span></div>


