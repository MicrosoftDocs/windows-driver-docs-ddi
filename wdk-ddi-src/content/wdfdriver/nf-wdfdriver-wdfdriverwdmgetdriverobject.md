---
UID: NF:wdfdriver.WdfDriverWdmGetDriverObject
title: WdfDriverWdmGetDriverObject function (wdfdriver.h)
description: The WdfDriverWdmGetDriverObject method retrieves a pointer to the Windows Driver Model (WDM) driver object that is associated with a specified framework driver object.
old-location: wdf\wdfdriverwdmgetdriverobject.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfDriverWdmGetDriverObject function"]
ms.keywords: DFDriverObjectRef_f196dc43-394e-4839-a64d-8af756f5a374.xml, WdfDriverWdmGetDriverObject, WdfDriverWdmGetDriverObject method, kmdf.wdfdriverwdmgetdriverobject, wdf.wdfdriverwdmgetdriverobject, wdfdriver/WdfDriverWdmGetDriverObject
req.header: wdfdriver.h
req.include-header: Wdf.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDriverWdmGetDriverObject
 - wdfdriver/WdfDriverWdmGetDriverObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDriverWdmGetDriverObject
---

# WdfDriverWdmGetDriverObject function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDriverWdmGetDriverObject</b> method retrieves a pointer to the Windows Driver Model (WDM) driver object that is associated with a specified framework driver object.

## -parameters

### -param Driver [in]


A handle to the driver's framework driver object that the driver obtained from a previous call to <a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a> or <a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfgetdriver">WdfGetDriver</a>.

## -returns

<b>WdfDriverWdmGetDriverObject</b> returns a pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a> structure. A system bug check occurs if the <i>Driver</i> handle is invalid.

## -remarks

The pointer that the <b>WdfDriverWdmGetDriverObject</b> method returns is valid until the framework driver object is deleted. If the driver provides an <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> function for the framework driver object, the pointer is valid until the callback function returns.


#### Examples

The following code example obtains a pointer to the WDM driver object that is associated with a specified framework driver object.

```cpp
PDRIVER_OBJECT  pDrvObj;

pDrvObj = WdfDriverWdmGetDriverObject(Driver);
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a>



<a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfgetdriver">WdfGetDriver</a>
