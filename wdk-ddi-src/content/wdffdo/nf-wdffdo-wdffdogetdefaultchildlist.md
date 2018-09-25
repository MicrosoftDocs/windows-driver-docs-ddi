---
UID: NF:wdffdo.WdfFdoGetDefaultChildList
title: WdfFdoGetDefaultChildList function
author: windows-driver-content
description: The WdfFdoGetDefaultChildList method returns a handle to a specified device's default child list.
old-location: wdf\wdffdogetdefaultchildlist.htm
tech.root: wdf
ms.assetid: b90c82ad-0531-4564-b30d-48e980282e85
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_b91b8c48-179f-42e5-8015-67eaf1b38226.xml, WdfFdoGetDefaultChildList, WdfFdoGetDefaultChildList method, kmdf.wdffdogetdefaultchildlist, wdf.wdffdogetdefaultchildlist, wdffdo/WdfFdoGetDefaultChildList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffdo.h
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
-	WdfFdoGetDefaultChildList
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfFdoGetDefaultChildList function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfFdoGetDefaultChildList</b> method returns a handle to a specified device's default child list.


## -parameters




### -param Fdo [in]

A handle to a framework device object.


## -returns



If the operation succeeds, <b>WdfFdoGetDefaultChildList</b> returns a handle to the default child list that is associated with the device that is specified by <i>Fdo</i>. Otherwise the method returns <b>NULL</b>.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



Before calling <b>WdfFdoGetDefaultChildList</b>, your driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547258">WdfFdoInitSetDefaultChildListConfig</a> to configure the default child list. Otherwise, <b>WdfFdoGetDefaultChildList</b> returns <b>NULL</b>.

For more information about child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

The following code example obtains a handle to a device's default child list.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFCHILDLIST  list;

list = WdfFdoGetDefaultChildList(Device);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547258">WdfFdoInitSetDefaultChildListConfig</a>
 

 

