---
UID: NF:wdffdo.WdfFdoGetDefaultChildList
title: WdfFdoGetDefaultChildList function
author: windows-driver-content
description: The WdfFdoGetDefaultChildList method returns a handle to a specified device's default child list.
old-location: wdf\wdffdogetdefaultchildlist.htm
old-project: wdf
ms.assetid: b90c82ad-0531-4564-b30d-48e980282e85
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , C, D, DFDeviceObjectFdoPdoRef_b91b8c48-179f-42e5-8015-67eaf1b38226.xml, F, G, L, W, WdfFdoGetDefaultChildList, WdfFdoGetDefaultChildList method, a, d, e, f, h, i, kmdf.wdffdogetdefaultchildlist, l, o, s, t, u, wdf.wdffdogetdefaultchildlist, wdffdo/WdfFdoGetDefaultChildList"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfFdoGetDefaultChildList
product: Windows
targetos: Windows
req.typenames: WDF_DRIVER_VERSION_AVAILABLE_PARAMS, *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product: Windows 10 or later.
---

# WdfFdoGetDefaultChildList function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfFdoGetDefaultChildList</b> method returns a handle to a specified device's default child list.


## -syntax


````
WDFCHILDLIST WdfFdoGetDefaultChildList(
  _In_ WDFDEVICE Fdo
);
````


## -parameters




### -param Fdo [in]

A handle to a framework device object.


## -returns



If the operation succeeds, <b>WdfFdoGetDefaultChildList</b> returns a handle to the default child list that is associated with the device that is specified by <i>Fdo</i>. Otherwise the method returns <b>NULL</b>.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



Before calling <b>WdfFdoGetDefaultChildList</b>, your driver must call <a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a> to configure the default child list. Otherwise, <b>WdfFdoGetDefaultChildList</b> returns <b>NULL</b>.

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

<a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFdoGetDefaultChildList method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

