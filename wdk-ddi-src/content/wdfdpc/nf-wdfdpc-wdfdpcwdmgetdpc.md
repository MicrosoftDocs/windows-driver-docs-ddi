---
UID: NF:wdfdpc.WdfDpcWdmGetDpc
title: WdfDpcWdmGetDpc function (wdfdpc.h)
description: The WdfDpcWdmGetDpc method returns a pointer to the KDPC structure that is associated with a specified framework DPC object.
old-location: wdf\wdfdpcwdmgetdpc.htm
tech.root: wdf
ms.assetid: a4ca55f9-0fbd-4969-8807-baa79099cff0
ms.date: 02/26/2018
keywords: ["WdfDpcWdmGetDpc function"]
ms.keywords: DFDpcObjectRef_26bd69e5-277b-4af4-a5b7-659670b39fbb.xml, WdfDpcWdmGetDpc, WdfDpcWdmGetDpc method, kmdf.wdfdpcwdmgetdpc, wdf.wdfdpcwdmgetdpc, wdfdpc/WdfDpcWdmGetDpc
f1_keywords:
 - "wdfdpc/WdfDpcWdmGetDpc"
req.header: wdfdpc.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDpcWdmGetDpc
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDpcWdmGetDpc function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDpcWdmGetDpc</b> method returns a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KDPC</a> structure that is associated with a specified framework DPC object.


## -parameters




### -param Dpc [in]

A handle to a framework DPC object.


## -returns



<b>WdfDpcWdmGetDpc</b> returns a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KDPC</a> structure that is associated with the specified framework DPC object.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The framework creates a KDPC structure when a framework-based driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nf-wdfdpc-wdfdpccreate">WdfDpcCreate</a> to create a DPC object. 

A driver might call <b>WdfDpcWdmGetDpc</b> from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a> callback function.

The pointer that <b>WdfDpcWdmGetDpc</b> returns is valid until the framework DPC object is deleted. If the driver provides an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> function for the framework DPC object, the pointer is valid until the callback function returns.


#### Examples

The following code example returns a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KDPC</a> structure that is associated with a specified DPC object. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nf-wdfdpc-wdfdpccreate">WdfDpcCreate</a> code example shows how the specified DPC object was created.

```cpp
PKDPC pWdmDpc;

pWdmDpc = WdfDpcWdmGetDpc(PDevExt->CompleteWriteDpc);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KDPC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/ns-wdfdpc-_wdf_dpc_config">WDF_DPC_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nf-wdfdpc-wdfdpccreate">WdfDpcCreate</a>
 

 

