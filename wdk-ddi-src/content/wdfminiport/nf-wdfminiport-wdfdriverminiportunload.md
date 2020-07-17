---
UID: NF:wdfminiport.WdfDriverMiniportUnload
title: WdfDriverMiniportUnload function (wdfminiport.h)
description: The WdfDriverMiniportUnload method deletes a specified miniport driver's framework driver object.
old-location: wdf\wdfdriverminiportunload.htm
tech.root: wdf
ms.assetid: 57220a12-e53d-482a-afb6-09bfbbf0d870
ms.date: 02/26/2018
keywords: ["WdfDriverMiniportUnload function"]
ms.keywords: DFDriverObjectRef_aac24375-fae4-4310-b273-d3d2f4c13d69.xml, WdfDriverMiniportUnload, WdfDriverMiniportUnload method, kmdf.wdfdriverminiportunload, wdf.wdfdriverminiportunload, wdfminiport/WdfDriverMiniportUnload
f1_keywords:
 - "wdfminiport/WdfDriverMiniportUnload"
 - "WdfDriverMiniportUnload"
req.header: wdfminiport.h
req.include-header: Wdfminiport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDriverMiniportUnload
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDriverMiniportUnload function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDriverMiniportUnload</b> method deletes a specified miniport driver's framework driver object.


## -parameters




### -param Driver [in]

A handle to the driver's framework driver object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfgetdriver">WdfGetDriver</a>.


## -remarks



A miniport driver calls the <b>WdfDriverMiniportUnload</b> method when the miniport driver is about to be unloaded. The method calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_unload">EvtDriverUnload</a> event callback function and deletes the driver's framework driver object.

Typically, a miniport driver calls <b>WdfDriverMiniportUnload</b> from within a driver-supplied unload routine that is defined by the port driver's architecture.

For more information about miniport drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-kmdf-miniport-drivers">Using Kernel-Mode Driver Framework with Miniport Drivers</a>.


#### Examples

The following code example deletes a specified miniport driver's framework driver object.

```cpp
WdfDriverMiniportUnload(WdfGetDriver());
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_unload">EvtDriverUnload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfminiport/nf-wdfminiport-wdfdeviceminiportcreate">WdfDeviceMiniportCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfgetdriver">WdfGetDriver</a>
 

 

