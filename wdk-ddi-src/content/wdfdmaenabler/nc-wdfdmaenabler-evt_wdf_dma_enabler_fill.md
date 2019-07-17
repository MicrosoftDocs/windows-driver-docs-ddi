---
UID: NC:wdfdmaenabler.EVT_WDF_DMA_ENABLER_FILL
title: EVT_WDF_DMA_ENABLER_FILL (wdfdmaenabler.h)
description: A driver's EvtDmaEnablerFill event callback function allocates a device's DMA buffers.
old-location: wdf\evtdmaenablerfill.htm
tech.root: wdf
ms.assetid: 3da947b4-76f9-492f-b8e2-b52aa7812b26
ms.date: 02/26/2018
ms.keywords: DFDmaObjectRef_3546c1f6-cb96-4b6e-bafa-25a1d15b00c5.xml, EVT_WDF_DMA_ENABLER_FILL, EVT_WDF_DMA_ENABLER_FILL callback, EvtDmaEnablerFill, EvtDmaEnablerFill callback function, kmdf.evtdmaenablerfill, wdf.evtdmaenablerfill, wdfdmaenabler/EvtDmaEnablerFill
ms.topic: callback
f1_keywords:
 - "wdfdmaenabler/EvtDmaEnablerFill"
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- WdfDmaEnabler.h
api_name:
- EvtDmaEnablerFill
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DMA_ENABLER_FILL callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDmaEnablerFill</i> event callback function allocates a device's DMA buffers.


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object.  


## -returns



<i>EvtDmaEnablerFill</i> must return STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>, if it encounters no errors. Otherwise, this callback function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 




## -remarks



To register an <i>EvtDmaEnablerFill</i> callback function, a function driver for a DMA device places the callback function's address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> structure before the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>.

For more information about the <i>EvtDmaEnablerFill</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-power-management-for-dma-devices">Supporting Power Management for DMA Devices</a>.

The <i>EvtDmaEnablerFill</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.


#### Examples

To define an <i>EvtDmaEnablerFill</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDmaEnablerFill</i> callback function that is named <i>MyDmaEnablerFill</i>, use the <b>EVT_WDF_DMA_ENABLER_FILL</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DMA_ENABLER_FILL MyDmaEnablerFill;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
 MyDmaEnablerFill (
    WDFDMAENABLER  DmaEnabler
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DMA_ENABLER_FILL</b> function type is defined in the WdfDmaEnabler.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DMA_ENABLER_FILL</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_flush">EvtDmaEnablerFlush</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>
 

 

