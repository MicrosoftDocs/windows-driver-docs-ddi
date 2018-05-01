---
UID: NF:wdfdriver.WdfDriverIsVersionAvailable
title: WdfDriverIsVersionAvailable function
author: windows-driver-content
description: The WdfDriverIsVersionAvailable method returns a Boolean value that indicates whether the driver is running with a specified version of the Kernel-Mode Driver Framework library.
old-location: wdf\wdfdriverisversionavailable.htm
old-project: wdf
ms.assetid: 5635b99d-c58d-4a17-bb51-2dc38e51421a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDriverObjectRef_56291c91-1c81-486d-89ce-948d037b8bc4.xml, WdfDriverIsVersionAvailable, WdfDriverIsVersionAvailable method, kmdf.wdfdriverisversionavailable, wdf.wdfdriverisversionavailable, wdfdriver/WdfDriverIsVersionAvailable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfDriverIsVersionAvailable
product: Windows
targetos: Windows
req.typenames: 
---

# WdfDriverIsVersionAvailable function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDriverIsVersionAvailable</b> method returns a Boolean value that indicates whether the driver is running with a specified version of the Kernel-Mode Driver Framework library.


## -parameters




### -param Driver [in]

A handle to the driver's framework driver object that the driver obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff547336">WdfGetDriver</a>.


### -param VersionAvailableParams [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551306">WDF_DRIVER_VERSION_AVAILABLE_PARAMS</a> structure that identifies a version of the framework library.


## -returns



<b>WdfDriverIsVersionAvailable</b> returns <b>TRUE</b> if the driver is running with the version of the library that the <i>VersionAvailableParams</i> parameter specifies. 

The method returns <b>FALSE</b> if the driver is not running with the specified library version or if the WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure is invalid.

A system bug check occurs if the <i>Driver</i> handle is invalid.






## -remarks



For more information about library versions, see <a href="https://msdn.microsoft.com/51db6f3c-45cb-46a7-9dd4-2bab67893fea">Framework Library Versioning</a>.


#### Examples

The following code example reports an error if it detects an unexpected library version number.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_DRIVER_VERSION_AVAILABLE_PARAMS ver;

WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT(&amp;ver, 1, 0);
if (!WdfDriverIsVersionAvailable(
                                 driver,
                                 &amp;ver
                                 )) {
    DbgPrint("Unexpected library version.\n");
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551306">WDF_DRIVER_VERSION_AVAILABLE_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547211">WdfDriverRetrieveVersionString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547336">WdfGetDriver</a>
 

 

