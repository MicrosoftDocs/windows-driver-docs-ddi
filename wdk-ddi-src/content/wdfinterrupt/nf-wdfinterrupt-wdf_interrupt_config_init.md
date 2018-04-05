---
UID: NF:wdfinterrupt.WDF_INTERRUPT_CONFIG_INIT
title: WDF_INTERRUPT_CONFIG_INIT function
author: windows-driver-content
description: The WDF_INTERRUPT_CONFIG_INIT function initializes a WDF_INTERRUPT_CONFIG structure.
old-location: wdf\wdf_interrupt_config_init.htm
old-project: wdf
ms.assetid: e81ec3da-a863-467f-82ec-1fa7ee6401b1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFInterruptObjectRef_eb73ee25-bee4-4c0a-a070-7893bd5b699a.xml, WDF_INTERRUPT_CONFIG_INIT, WDF_INTERRUPT_CONFIG_INIT function, kmdf.wdf_interrupt_config_init, wdf.wdf_interrupt_config_init, wdfinterrupt/WDF_INTERRUPT_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfinterrupt.h
api_name:
-	WDF_INTERRUPT_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---

# WDF_INTERRUPT_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_INTERRUPT_CONFIG_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure.


## -parameters




### -param Configuration [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure.


### -param EvtInterruptIsr [in]

A pointer to the driver's <a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a> callback function.


### -param EvtInterruptDpc [in, optional]

A pointer to the driver's <a href="https://msdn.microsoft.com/d2d505e0-aeac-4871-8c60-d026b2833043">EvtInterruptDpc</a> callback function, or <b>NULL</b>.


## -returns



None




## -remarks



The <b>WDF_INTERRUPT_CONFIG_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure and sets its <b>Size</b> member to the structure's size. It also sets the structure's <b>ShareVector</b> member to <b>WdfUseDefault</b> and stores the specified callback function pointers. Finally, it sets the <b>ReportInactiveOnPowerDown</b>  member of the specified <b>WDF_INTERRUPT_CONFIG</b> structure to <b>WdfDefault</b>.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

For a code example that uses <b>WDF_INTERRUPT_CONFIG_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547345">WdfInterruptCreate</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/d2d505e0-aeac-4871-8c60-d026b2833043">EvtInterruptDpc</a>



<a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a>
 

 

