---
UID: NF:wdfinterrupt.WDF_INTERRUPT_INFO_INIT
title: WDF_INTERRUPT_INFO_INIT function
author: windows-driver-content
description: The WDF_INTERRUPT_INFO_INIT function initializes a WDF_INTERRUPT_INFO structure.
old-location: wdf\wdf_interrupt_info_init.htm
old-project: wdf
ms.assetid: 4c23f270-9ea3-475f-81d8-c003b2aca44b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFInterruptObjectRef_5b885d42-7ce9-4ac2-b97b-c41906298c22.xml, WDF_INTERRUPT_INFO_INIT, WDF_INTERRUPT_INFO_INIT function, kmdf.wdf_interrupt_info_init, wdf.wdf_interrupt_info_init, wdfinterrupt/WDF_INTERRUPT_INFO_INIT
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
-	WDF_INTERRUPT_INFO_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_INTERRUPT_INFO_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_INTERRUPT_INFO_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a> structure.


## -parameters




### -param Info [out]

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a> structure.


## -returns



None




## -remarks



The <b>WDF_INTERRUPT_INFO_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a> structure and sets the structure's <b>Size</b> member.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

For a code example that uses <b>WDF_INTERRUPT_INFO_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547367">WdfInterruptGetInfo</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547367">WdfInterruptGetInfo</a>
 

 

