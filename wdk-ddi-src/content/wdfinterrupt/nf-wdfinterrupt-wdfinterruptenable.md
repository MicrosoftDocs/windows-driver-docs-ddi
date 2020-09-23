---
UID: NF:wdfinterrupt.WdfInterruptEnable
title: WdfInterruptEnable function (wdfinterrupt.h)
description: The WdfInterruptEnable method enables a specified device interrupt by calling the driver's EvtInterruptEnable callback function.
old-location: wdf\wdfinterruptenable.htm
tech.root: wdf
ms.assetid: e2ffab7f-b6bf-4707-9a3d-9619330b2af1
ms.date: 02/26/2018
keywords: ["WdfInterruptEnable function"]
ms.keywords: DFInterruptObjectRef_4fa737c9-fae4-4d3c-9a27-165f5348c66c.xml, WdfInterruptEnable, WdfInterruptEnable method, kmdf.wdfinterruptenable, wdf.wdfinterruptenable, wdfinterrupt/WdfInterruptEnable
req.header: wdfinterrupt.h
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
 - WdfInterruptEnable
 - wdfinterrupt/WdfInterruptEnable
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
 - WdfInterruptEnable
---

# WdfInterruptEnable function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfInterruptEnable</b> method enables a specified device interrupt by calling the driver's <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_enable">EvtInterruptEnable</a> callback function.

## -parameters

### -param Interrupt 

[in]
A handle to a framework interrupt object.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.



Most framework-based drivers don't need to call <b>WdfInterruptEnable</b>, because the framework calls the driver's <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_enable">EvtInterruptEnable</a> callback function each time the device enters its working (D0) state.

For <a href="/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt objects</a>, the framework calls <b>WdfInterruptEnable</b> at PASSIVE_LEVEL.

Do not call <b>WdfInterruptEnable</b> from an arbitrary thread context,  such as a <a href="/windows-hardware/drivers/wdf/request-handlers">request handler</a>.

For more information about handling interrupts in framework-based drivers, see <a href="/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.


#### Examples

The following code example enables the device interrupt that is associated with a specified interrupt object.

```cpp
WdfInterruptEnable(Interrupt);
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_enable">EvtInterruptEnable</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptdisable">WdfInterruptDisable</a>