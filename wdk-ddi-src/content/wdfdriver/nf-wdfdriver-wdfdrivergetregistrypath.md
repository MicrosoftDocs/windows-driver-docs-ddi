---
UID: NF:wdfdriver.WdfDriverGetRegistryPath
title: WdfDriverGetRegistryPath function
author: windows-driver-content
description: The WdfDriverGetRegistryPath method retrieves the path to the driver's registry key in the registry's Services tree.
old-location: wdf\wdfdrivergetregistrypath.htm
old-project: wdf
ms.assetid: 5f237d2e-5ffd-40af-8cd8-ea1414807086
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFDriverObjectRef_a21bcb6e-2211-4727-bb87-bb912f8a173b.xml, PFN_WDFDRIVERGETREGISTRYPATH, kmdf.wdfdrivergetregistrypath, wdf.wdfdrivergetregistrypath, WdfDriverGetRegistryPath, WdfDriverGetRegistryPath method, wdfdriver/WdfDriverGetRegistryPath
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfDriverGetRegistryPath
product: Windows
targetos: Windows
req.typenames: WDF_DRIVER_INIT_FLAGS
req.product: Windows 10 or later.
---

# WdfDriverGetRegistryPath function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDriverGetRegistryPath</b> method retrieves the path to the driver's registry key in the registry's <a href="https://msdn.microsoft.com/library/windows/hardware/dn926947">Services</a> tree.


## -syntax


````
PWSTR WdfDriverGetRegistryPath(
  _In_ WDFDRIVER Driver
);
````


## -parameters




### -param Driver [in]

A handle to the driver's framework driver object, obtained by a previous call to <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a> or <a href="..\wdfdriver\nf-wdfdriver-wdfgetdriver.md">WdfGetDriver</a>. 


## -returns



<b>WdfDriverGetRegistryPath</b> returns a pointer to a NULL-terminated Unicode string that represents the driver's registry path. A system bug check occurs if the <i>Driver</i> handle is invalid.




## -remarks



The registry path string that <b>WdfDriverGetRegistryPath</b> returns is obtained from the <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that the driver received as input to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine. 

For more information about the registry, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.


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

<a href="..\wdfdriver\nf-wdfdriver-wdfgetdriver.md">WdfGetDriver</a>



<a href="..\wdfdriver\nf-wdfdriver-wdfdriveropenparametersregistrykey.md">WdfDriverOpenParametersRegistryKey</a>



<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDriverGetRegistryPath method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

