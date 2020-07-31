---
UID: NF:wdfdpc.WdfDpcCancel
title: WdfDpcCancel function (wdfdpc.h)
description: The WdfDpcCancel method attempts to cancel the execution of a DPC object's scheduled EvtDpcFunc callback function.
old-location: wdf\wdfdpccancel.htm
tech.root: wdf
ms.assetid: 6eb56c5b-d198-4542-a239-c54b49561196
ms.date: 02/26/2018
keywords: ["WdfDpcCancel function"]
ms.keywords: DFDpcObjectRef_4efcdae1-0c0a-4808-a1d8-640dea3555cb.xml, WdfDpcCancel, WdfDpcCancel method, kmdf.wdfdpccancel, wdf.wdfdpccancel, wdfdpc/WdfDpcCancel
f1_keywords:
 - "wdfdpc/WdfDpcCancel"
 - "WdfDpcCancel"
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
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDpcCancel
targetos: Windows
req.typenames: 
---

# WdfDpcCancel function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDpcCancel</b> method attempts to cancel the execution of a DPC object's scheduled <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a> callback function.


## -parameters




### -param Dpc [in]

A handle to a framework DPC object.


### -param Wait [in]

A Boolean value that, if <b>TRUE</b>, indicates that the <b>WdfDpcCancel</b> method will not return until the DPC object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a> callback function is either canceled or finishes executing. If <b>FALSE</b>, the <b>WdfDpcCancel</b> method returns immediately.


## -returns



<b>WdfDpcCancel</b> returns <b>TRUE</b> if the specified DPC object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a> callback function was in the system's DPC queue. The method returns <b>FALSE</b> if the callback function was not in the DPC queue, either because the callback function was executing or because it had finished executing.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If the specified DPC object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a> callback function is in the system's DPC queue, it is removed from the queue. If the <i>EvtDpcFunc</i> function is not in the queue, it is either executing or has finished executing. 

If the <i>Wait</i> parameter is <b>TRUE</b>, <b>WdfDpcCancel</b> must be called at IRQL = PASSIVE_LEVEL. If the <i>Wait</i> parameter is <b>FALSE</b>, <b>WdfDpcCancel</b> can be called at any IRQL.


#### Examples

The following code example cancels the execution of the callback function that is associated with the DPC object that the code example in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nf-wdfdpc-wdfdpccreate">WdfDpcCreate</a> topic created.

```cpp
WdfDpcCancel(
             PDevExt->CompleteWriteDpc,
             TRUE
             );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a>
 

 

