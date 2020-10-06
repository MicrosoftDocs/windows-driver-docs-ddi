---
UID: NF:wdfinterrupt.WdfInterruptWdmGetInterrupt
title: WdfInterruptWdmGetInterrupt function (wdfinterrupt.h)
description: The WdfInterruptWdmGetInterrupt method returns a pointer to the WDM interrupt object that is associated with a specified framework interrupt object.
old-location: wdf\wdfinterruptwdmgetinterrupt.htm
tech.root: wdf
ms.assetid: b301e9f6-264d-43d9-a344-b34dcd659d04
ms.date: 02/26/2018
keywords: ["WdfInterruptWdmGetInterrupt function"]
ms.keywords: DFInterruptObjectRef_72a56280-07d3-43c1-99f9-68dc3323fe86.xml, WdfInterruptWdmGetInterrupt, WdfInterruptWdmGetInterrupt method, kmdf.wdfinterruptwdmgetinterrupt, wdf.wdfinterruptwdmgetinterrupt, wdfinterrupt/WdfInterruptWdmGetInterrupt
req.header: wdfinterrupt.h
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
req.irql: <= DIRQL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfInterruptWdmGetInterrupt
 - wdfinterrupt/WdfInterruptWdmGetInterrupt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfInterruptWdmGetInterrupt
---

# WdfInterruptWdmGetInterrupt function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfInterruptWdmGetInterrupt</b> method returns a pointer to the WDM interrupt object that is associated with a specified framework interrupt object.

## -parameters

### -param Interrupt 

[in]
A handle to a framework interrupt object.

## -returns

The <b>WdfInterruptWdmGetInterrupt</b> method returns a pointer to a <a href="/windows-hardware/drivers/kernel/eprocess">KINTERRUPT</a> structure. This method returns <b>NULL</b> if it is called before the driver's <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_enable">EvtInterruptEnable</a> callback function is called or after the driver's <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_disable">EvtInterruptDisable</a> callback function returns.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

The pointer that the <b>WdfInterruptWdmGetInterrupt</b> method returns is valid until the driver's <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_disable">EvtInterruptDisable</a> callback function returns. 

For more information about handling interrupts in framework-based drivers, see <a href="/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.


#### Examples

The following code example obtains a pointer to the KINTERRUPT structure that is associated with a specified framework interrupt object.

```cpp
PKINTERRUPT  wdmInterrupt;

wdmInterrupt = WdfInterruptWdmGetInterrupt(Interrupt);
```

## -see-also

<a href="/windows-hardware/drivers/kernel/eprocess">KINTERRUPT</a>