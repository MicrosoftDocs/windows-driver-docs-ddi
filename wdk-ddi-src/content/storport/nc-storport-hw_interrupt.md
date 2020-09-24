---
UID: NC:storport.HW_INTERRUPT
title: HW_INTERRUPT (storport.h)
description: The Storport driver calls the HwStorInterrupt routine after the HBA generates an interrupt request.
old-location: storage\hwstorinterrupt.htm
tech.root: storage
ms.assetid: 3c61d947-3e05-4750-a50c-be9b2dc573f0
ms.date: 03/29/2018
keywords: ["HW_INTERRUPT callback function"]
ms.keywords: HW_INTERRUPT, HwStorInterrupt, HwStorInterrupt routine [Storage Devices], storage.hwstorinterrupt, stormini_17f68641-1cfd-47b3-a52f-be98f96e693f.xml, storport/HwStorInterrupt
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
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
req.irql: DIRQL
targetos: Windows
req.typenames: 
f1_keywords:
 - HW_INTERRUPT
 - storport/HW_INTERRUPT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HwStorInterrupt
---

# HW_INTERRUPT callback function


## -description

The Storport driver calls the <b>HwStorInterrupt</b> routine after the HBA generates an interrupt request.

## -parameters

### -param DeviceExtension

A pointer to the miniport driver's per HBA storage area.

## -returns

If the miniport driver finds that its HBA did not generate the interrupt, <b>HwStorInterrupt</b> should return <b>FALSE</b> as soon as possible. The <b>HwStorInterrupt</b> routine should return within 50 microseconds.

## -remarks

The name <b>HwStorInterrupt</b> is just a placeholder. The actual prototype of this routine is defined in <i>Storport.h</i> as follows:

<pre class="syntax" xml:space="preserve"><code>typedef
BOOLEAN
HW_INTERRUPT (
  IN PVOID  DeviceExtension
  );</code></pre>
The <b>HwStorInterrupt</b> routine should return within 50 microseconds, ideally as short a time as possible. Therefore, all activity does not have to occur at high IRQL should be deferred to the <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_dpc_routine">HwStorDpcRoutine</a> that is defined in the miniport driver and issued by using <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportissuedpc">StorPortIssueDpc</a>.  The latency of the DPC is very low, and it will be called immediately after the return from high IRQL.

The port driver calls the <b>HwStorInterrupt</b> routine at DIRQL.


#### Examples

To define an <b>HwStorInterrupt</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorInterrupt</b> callback routine that is named <i>MyHwInterrupt</i>, use the <b>HW_INTERRUPT</b> type as shown in this code example:


```
HW_INTERRUPT MyHwInterrupt;
```

Then, implement your callback routine as follows:


```
_Use_decl_annotations_
BOOLEAN
MyHwInterrupt (
  _In_ PVOID  DeviceExtension
  );
  {
      ...
  }
```

The <b>HW_INTERRUPT</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_INTERRUPT</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_dpc_routine">HwStorDpcRoutine</a>



<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportissuedpc">StorPortIssueDpc</a>