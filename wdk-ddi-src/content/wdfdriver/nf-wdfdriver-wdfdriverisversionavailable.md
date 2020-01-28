---
UID: NF:wdfdriver.WdfDriverIsVersionAvailable
title: WdfDriverIsVersionAvailable function (wdfdriver.h)
description: The WdfDriverIsVersionAvailable method returns a Boolean value that indicates whether the driver is running with a specified version of the Kernel-Mode Driver Framework library.
old-location: wdf\wdfdriverisversionavailable.htm
tech.root: wdf
ms.assetid: 5635b99d-c58d-4a17-bb51-2dc38e51421a
ms.date: 02/26/2018
ms.keywords: DFDriverObjectRef_56291c91-1c81-486d-89ce-948d037b8bc4.xml, WdfDriverIsVersionAvailable, WdfDriverIsVersionAvailable method, kmdf.wdfdriverisversionavailable, wdf.wdfdriverisversionavailable, wdfdriver/WdfDriverIsVersionAvailable
f1_keywords:
 - "wdfdriver/WdfDriverIsVersionAvailable"
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
- WdfDriverIsVersionAvailable
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDriverIsVersionAvailable function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDriverIsVersionAvailable</b> method returns a Boolean value that indicates whether the driver is running with a specified version of the Kernel-Mode Driver Framework library.


## -parameters




### -param Driver [in]

A handle to the driver's framework driver object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfgetdriver">WdfGetDriver</a>.


### -param VersionAvailableParams [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/ns-wdfdriver-_wdf_driver_version_available_params">WDF_DRIVER_VERSION_AVAILABLE_PARAMS</a> structure that identifies a version of the framework library.


## -returns



<b>WdfDriverIsVersionAvailable</b> returns <b>TRUE</b> if the driver is running with the version of the library that the <i>VersionAvailableParams</i> parameter specifies. 

The method returns <b>FALSE</b> if the driver is not running with the specified library version or if the WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure is invalid.

A system bug check occurs if the <i>Driver</i> handle is invalid.






## -remarks



For more information about library versions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-library-versioning">Framework Library Versioning</a>.


#### Examples

The following code example reports an error if it detects an unexpected library version number.

```cpp
WDF_DRIVER_VERSION_AVAILABLE_PARAMS ver;

WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT(&ver, 1, 0);
if (!WdfDriverIsVersionAvailable(
                                 driver,
                                 &ver
                                 )) {
    DbgPrint("Unexpected library version.\n");
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/ns-wdfdriver-_wdf_driver_version_available_params">WDF_DRIVER_VERSION_AVAILABLE_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdriverretrieveversionstring">WdfDriverRetrieveVersionString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfgetdriver">WdfGetDriver</a>
 

 

