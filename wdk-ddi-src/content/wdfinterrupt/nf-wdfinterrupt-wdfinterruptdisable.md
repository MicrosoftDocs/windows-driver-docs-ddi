---
UID: NF:wdfinterrupt.WdfInterruptDisable
title: WdfInterruptDisable function (wdfinterrupt.h)
description: The WdfInterruptDisable method disables a specified device interrupt by calling the driver's EvtInterruptDisable callback function.
old-location: wdf\wdfinterruptdisable.htm
tech.root: wdf
ms.assetid: 8ece6a3f-2f25-4143-8f0e-c65c02794cc4
ms.date: 02/26/2018
keywords: ["WdfInterruptDisable function"]
ms.keywords: DFInterruptObjectRef_05ca577a-87b3-419a-a3f8-ee57b0765701.xml, WdfInterruptDisable, WdfInterruptDisable method, kmdf.wdfinterruptdisable, wdf.wdfinterruptdisable, wdfinterrupt/WdfInterruptDisable
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
 - WdfInterruptDisable
 - wdfinterrupt/WdfInterruptDisable
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
 - WdfInterruptDisable
---

# WdfInterruptDisable function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfInterruptDisable</b> method disables a specified device interrupt by calling the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_disable">EvtInterruptDisable</a> callback function.

## -parameters

### -param Interrupt 

[in]
A handle to a framework interrupt object.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.



Most framework-based drivers don't need to call <b>WdfInterruptDisable</b>, because the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_disable">EvtInterruptDisable</a> callback function each time the device leaves its working (D0) state.

For <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt objects</a>, the framework calls <b>WdfInterruptDisable</b> at PASSIVE_LEVEL.

Do not call <b>WdfInterruptDisable</b> from an arbitrary thread context,  such as a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">request handler</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.


#### Examples

The following code example disables the device interrupt that is associated with a specified interrupt object.

```cpp
WdfInterruptDisable(Interrupt);
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_disable">EvtInterruptDisable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptenable">WdfInterruptEnable</a>

