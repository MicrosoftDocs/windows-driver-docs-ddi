---
UID: NF:wdfdriver.WdfDriverGetRegistryPath
title: WdfDriverGetRegistryPath function
author: windows-driver-content
description: The WdfDriverGetRegistryPath method retrieves the path to the driver's registry key in the registry's Services tree.
old-location: wdf\wdfdrivergetregistrypath.htm
old-project: wdf
ms.assetid: 5f237d2e-5ffd-40af-8cd8-ea1414807086
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDriverObjectRef_a21bcb6e-2211-4727-bb87-bb912f8a173b.xml, WdfDriverGetRegistryPath, WdfDriverGetRegistryPath method, kmdf.wdfdrivergetregistrypath, wdf.wdfdrivergetregistrypath, wdfdriver/WdfDriverGetRegistryPath
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
-	WdfDriverGetRegistryPath
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDriverGetRegistryPath function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDriverGetRegistryPath</b> method retrieves the path to the driver's registry key in the registry's <a href="https://msdn.microsoft.com/library/windows/hardware/dn926947">Services</a> tree.


## -parameters




### -param Driver [in]

A handle to the driver's framework driver object, obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff547336">WdfGetDriver</a>. 


## -returns



<b>WdfDriverGetRegistryPath</b> returns a pointer to a NULL-terminated Unicode string that represents the driver's registry path. A system bug check occurs if the <i>Driver</i> handle is invalid.




## -remarks



The registry path string that <b>WdfDriverGetRegistryPath</b> returns is obtained from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that the driver received as input to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine. 

For more information about the registry, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example obtains the path to a driver's registry key in the registry's <b>Services</b> tree.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PWSTR  registryPath;

registryPath = WdfDriverGetRegistryPath(driver);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547202">WdfDriverOpenParametersRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547336">WdfGetDriver</a>
 

 

