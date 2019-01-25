---
UID: NF:wdfchildlist.WdfChildListGetDevice
title: WdfChildListGetDevice function (wdfchildlist.h)
description: The WdfChildListGetDevice method returns a handle to the framework device object that represents the parent device of a specified child list.
old-location: wdf\wdfchildlistgetdevice.htm
tech.root: wdf
ms.assetid: 5d51ec82-4891-47f1-8fc1-b20cb611d7fe
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectChildListRef_3126e6d6-e0d4-4ad1-865e-e7ec36e3c593.xml, WdfChildListGetDevice, WdfChildListGetDevice method, kmdf.wdfchildlistgetdevice, wdf.wdfchildlistgetdevice, wdfchildlist/WdfChildListGetDevice
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfChildListGetDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfChildListGetDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfChildListGetDevice</b> method returns a handle to the framework device object that represents the parent device of a specified child list.


## -parameters




### -param ChildList [in]

A handle to a framework child-list object.


## -returns



<b>WdfChildListGetDevice</b> returns a handle to a framework device object.

A system bug check occurs if the driver supplies an invalid object handle.





## -remarks



For more information about child lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


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


