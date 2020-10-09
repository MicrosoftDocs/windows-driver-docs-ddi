---
UID: NF:wdfinterrupt.WDF_INTERRUPT_CONFIG_INIT
title: WDF_INTERRUPT_CONFIG_INIT function (wdfinterrupt.h)
description: The WDF_INTERRUPT_CONFIG_INIT function initializes a WDF_INTERRUPT_CONFIG structure.
old-location: wdf\wdf_interrupt_config_init.htm
tech.root: wdf
ms.assetid: e81ec3da-a863-467f-82ec-1fa7ee6401b1
ms.date: 02/26/2018
keywords: ["WDF_INTERRUPT_CONFIG_INIT function"]
ms.keywords: DFInterruptObjectRef_eb73ee25-bee4-4c0a-a070-7893bd5b699a.xml, WDF_INTERRUPT_CONFIG_INIT, WDF_INTERRUPT_CONFIG_INIT function, kmdf.wdf_interrupt_config_init, wdf.wdf_interrupt_config_init, wdfinterrupt/WDF_INTERRUPT_CONFIG_INIT
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_INTERRUPT_CONFIG_INIT
 - wdfinterrupt/WDF_INTERRUPT_CONFIG_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfinterrupt.h
api_name:
 - WDF_INTERRUPT_CONFIG_INIT
---

# WDF_INTERRUPT_CONFIG_INIT function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_INTERRUPT_CONFIG_INIT</b> function initializes a <a href="/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure.

## -parameters

### -param Configuration 

[out]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure.

### -param EvtInterruptIsr 

[in]
A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback function.

### -param EvtInterruptDpc 

[in, optional]
A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback function, or <b>NULL</b>.

## -remarks

The <b>WDF_INTERRUPT_CONFIG_INIT</b> function zeros the specified <a href="/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure and sets its <b>Size</b> member to the structure's size. It also sets the structure's <b>ShareVector</b> member to <b>WdfUseDefault</b> and stores the specified callback function pointers. Finally, it sets the <b>ReportInactiveOnPowerDown</b>  member of the specified <b>WDF_INTERRUPT_CONFIG</b> structure to <b>WdfDefault</b>.

For more information about handling interrupts in framework-based drivers, see <a href="/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.


#### Examples

For a code example that uses <b>WDF_INTERRUPT_CONFIG_INIT</b>, see <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a>