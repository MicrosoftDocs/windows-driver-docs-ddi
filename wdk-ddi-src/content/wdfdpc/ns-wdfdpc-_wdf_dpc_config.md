---
UID: NS:wdfdpc._WDF_DPC_CONFIG
title: "_WDF_DPC_CONFIG"
author: windows-driver-content
description: The WDF_DPC_CONFIG structure contains configuration information for a DPC object.
old-location: wdf\wdf_dpc_config.htm
tech.root: wdf
ms.assetid: e4203a9d-98f4-47f2-80ea-51074e4c0713
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_DPC_CONFIG, DFDpcObjectRef_797caee0-a119-4bae-837b-461e74022868.xml, PWDF_DPC_CONFIG, PWDF_DPC_CONFIG structure pointer, WDF_DPC_CONFIG, WDF_DPC_CONFIG structure, _WDF_DPC_CONFIG, kmdf.wdf_dpc_config, wdf.wdf_dpc_config, wdfdpc/PWDF_DPC_CONFIG, wdfdpc/WDF_DPC_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfdpc.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdpc.h
api_name:
-	WDF_DPC_CONFIG
product:
- Windows
targetos: Windows
req.typenames: WDF_DPC_CONFIG, *PWDF_DPC_CONFIG
---

# _WDF_DPC_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_DPC_CONFIG</b> structure contains configuration information for a DPC object.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field EvtDpcFunc

A pointer to the driver's <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function.


### -field AutomaticSerialization

A Boolean value that, if <b>TRUE</b>, indicates that the framework will synchronize execution of the DPC object's <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function with callback functions from other objects that are underneath the DPC object's parent. For more information, see the following Remarks section.


## -remarks



The <b>WDF_DPC_CONFIG</b> structure is used as input to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547140">WdfDpcCreate</a>. 

To initialize a <b>WDF_DPC_CONFIG</b> structure, your driver should first call <a href="https://msdn.microsoft.com/library/windows/hardware/ff551298">WDF_DPC_CONFIG_INIT</a> and then fill in structure members that <b>WDF_DPC_CONFIG_INIT</b> does not initialize.

Setting <b>AutomaticSerialization</b> to <b>TRUE</b> has no effect if the parent device object's <a href="https://msdn.microsoft.com/a251bf5c-c09b-4097-a9ed-82f2312ac408">synchronization scope</a> is set to <b>WdfSynchronizationScopeNone</b>.

Setting <b>AutomaticSerialization</b> to <b>TRUE</b> causes <a href="https://msdn.microsoft.com/library/windows/hardware/ff547140">WdfDpcCreate</a> to fail if the parent device object's <a href="https://msdn.microsoft.com/82b1fe8e-054c-4710-9a32-d620a62a070e">execution level</a> is set to <b>WdfExecutionLevelPassive</b>.

For more information about <b>AutomaticSerialization</b> and synchronizing driver callback functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.




## -see-also




<a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551298">WDF_DPC_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547140">WdfDpcCreate</a>
 

 

