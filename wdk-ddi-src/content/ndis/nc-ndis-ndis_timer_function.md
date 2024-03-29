---
UID: NC:ndis.NDIS_TIMER_FUNCTION
title: NDIS_TIMER_FUNCTION (ndis.h)
description: The NdisTimerFunction function is called by NDIS after a driver sets a one-shot or periodic timer when a timer fires.Note  You must declare the function by using the NDIS_TIMER_FUNCTION type.
old-location: netvista\nettimercallback.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_TIMER_FUNCTION callback function"]
ms.keywords: NDIS_TIMER_FUNCTION, NDIS_TIMER_FUNCTION callback, NdisTimerFunction, NdisTimerFunction callback function [Network Drivers Starting with Windows Vista], ndis/NdisTimerFunction, ndis_timer_ref_9040f7c2-905a-457d-a7c3-07253e2fb3da.xml, netvista.nettimercallback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NDIS_TIMER_FUNCTION
 - ndis/NDIS_TIMER_FUNCTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - NDIS_TIMER_FUNCTION
---

# NDIS_TIMER_FUNCTION callback function


## -description

The 
  <i>NdisTimerFunction</i> callback function is called by NDIS after a driver sets a one-shot or periodic timer when a
  timer fires.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>NDIS_TIMER_FUNCTION</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param SystemSpecific1 [in]


A pointer to a system-specific value that is reserved for system use.

### -param FunctionContext [in]


A pointer to a driver-supplied context area that the driver passed to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissettimerobject">NdisSetTimerObject</a> function. If the 
     <i>FunctionContext</i> parameter of 
     <b>NdisSetTimerObject</b> was <b>NULL</b>, NDIS uses the default value that the driver specified in the 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_timer_characteristics">
     NDIS_TIMER_CHARACTERISTICS</a> structure. The driver passed the structure to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatetimerobject">NdisAllocateTimerObject</a> function
     to initialize the associated timer object.

### -param SystemSpecific2 [in]


A pointer to a system-specific value that is reserved for system use.

### -param SystemSpecific3 [in]


A pointer to a system-specific value that is reserved for system use.

## -remarks

Any NDIS driver can have one or more 
    <i>NdisTimerFunction</i> callback functions. Each such 
    <i>NdisTimerFunction</i> callback must be associated with a different driver-allocated and initialized
    timer object.

The driver initializes a driver-allocated timer object by calling the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatetimerobject">
    NdisAllocateTimerObject</a> function.

A subsequent call to the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissettimerobject">NdisSetTimerObject</a> function causes the 
    <i>NdisTimerFunction</i> callback that is associated with the timer object to be run after a specified
    interval or periodically.

To cancel calls to 
    <i>NdisTimerFunction</i>, call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscanceltimerobject">NdisCancelTimerObject</a> function. NDIS
    might still call 
    <i>NdisTimerFunction</i> if the timeout has already expired before the call to 
    <b>NdisCancelTimerObject</b>.

If a 
    <i>NdisTimerFunction</i> callback shares resources with other driver functions, the driver should
    synchronize access to those resources with a spin lock.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>NdisTimerFunction</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>NdisTimerFunction</i> function that is named "MyTimerCallback", use the <b>NDIS_TIMER_FUNCTION</b> type as shown in this code example:


```
NDIS_TIMER_FUNCTION MyTimerCallback;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyTimerCallback(
    PVOID  SystemSpecific1,
    PVOID  FunctionContext,
    PVOID  SystemSpecific2,
    PVOID  SystemSpecific3
    )
  {...}
```

The <b>NDIS_TIMER_FUNCTION</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>NDIS_TIMER_FUNCTION</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/network/initializing-ndis-timers">Initializing NDIS Timers</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_timer_characteristics">NDIS_TIMER_CHARACTERISTICS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatetimerobject">NdisAllocateTimerObject</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscanceltimerobject">NdisCancelTimerObject</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissettimerobject">NdisSetTimerObject</a>



<a href="/windows-hardware/drivers/network/servicing-timers">Servicing Timers</a>



<a href="/windows-hardware/drivers/network/setting-and-clearing-timers">Setting and Clearing Timers</a>

