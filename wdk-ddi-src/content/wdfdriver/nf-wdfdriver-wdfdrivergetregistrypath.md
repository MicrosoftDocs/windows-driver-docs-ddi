---
UID: NF:wdfdriver.WdfDriverGetRegistryPath
title: WdfDriverGetRegistryPath function (wdfdriver.h)
description: The WdfDriverGetRegistryPath method retrieves the path to the driver's registry key in the registry's Services tree.
old-location: wdf\wdfdrivergetregistrypath.htm
tech.root: wdf
ms.assetid: 5f237d2e-5ffd-40af-8cd8-ea1414807086
ms.date: 02/26/2018
keywords: ["WdfDriverGetRegistryPath function"]
ms.keywords: DFDriverObjectRef_a21bcb6e-2211-4727-bb87-bb912f8a173b.xml, WdfDriverGetRegistryPath, WdfDriverGetRegistryPath method, kmdf.wdfdrivergetregistrypath, wdf.wdfdrivergetregistrypath, wdfdriver/WdfDriverGetRegistryPath
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDriverGetRegistryPath
 - wdfdriver/WdfDriverGetRegistryPath
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfDriverGetRegistryPath
---

# WdfDriverGetRegistryPath function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDriverGetRegistryPath</b> method retrieves the path to the driver's registry key in the registry's <a href="/windows-hardware/test/wpt/services">Services</a> tree.

## -parameters

### -param Driver 

[in]
A handle to the driver's framework driver object, obtained by a previous call to <a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a> or <a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfgetdriver">WdfGetDriver</a>.

## -returns

<b>WdfDriverGetRegistryPath</b> returns a pointer to a NULL-terminated Unicode string that represents the driver's registry path. A system bug check occurs if the <i>Driver</i> handle is invalid.

## -remarks

The registry path string that <b>WdfDriverGetRegistryPath</b> returns is obtained from the <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that the driver received as input to its <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine. 

For more information about the registry, see <a href="/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example obtains the path to a driver's registry key in the registry's <b>Services</b> tree.

```cpp
PWSTR  registryPath;

registryPath = WdfDriverGetRegistryPath(driver);
```

## -see-also

<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a>



<a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdriveropenparametersregistrykey">WdfDriverOpenParametersRegistryKey</a>



<a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfgetdriver">WdfGetDriver</a>