---
UID: NC:ndis.MINIPORT_CHECK_FOR_HANG
title: MINIPORT_CHECK_FOR_HANG (ndis.h)
description: NDIS calls a miniport driver's MiniportCheckForHangEx function to check the operational state of the miniport adapter that represents a network interface card (NIC).
old-location: netvista\miniportcheckforhangex.htm
tech.root: netvista
ms.assetid: ead0af85-0584-49de-82cc-8a059ebfdf4f
ms.date: 05/02/2018
ms.keywords: MINIPORT_CHECK_FOR_HANG, MINIPORT_CHECK_FOR_HANG callback, MiniportCheckForHangEx, MiniportCheckForHangEx callback function [Network Drivers Starting with Windows Vista], miniport_functions_ref_4dac5544-94b0-4be6-aa81-709bff9163a7.xml, ndis/MiniportCheckForHangEx, netvista.miniportcheckforhangex
f1_keywords:
 - "ndis/MiniportCheckForHangEx"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- MiniportCheckForHangEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_CHECK_FOR_HANG callback function


## -description

> [!WARNING]
> The *MiniportCheckForHangEx* and [*MiniportResetEx*](nc-ndis-miniport_reset.md) callback functions are discouraged for all NDIS 6.83 and later drivers. For more information, see [Check-for-Hang and Reset operations in NDIS 6.83 and later](https://docs.microsoft.com/windows-hardware/drivers/network/miniport-adapter-check-for-hang-and-reset-operations#check-for-hang-and-reset-operations-in-ndis-683-and-later).


NDIS calls a miniport driver's 
   <i>MiniportCheckForHangEx</i> function to check the operational state of the miniport adapter that represents a network interface card (NIC).
<div class="alert"><b>Note</b>  A miniport driver may declare this function by using the <b>MINIPORT_CHECK_FOR_HANG</b> type.
</div><div> </div><div class="alert"><b>Note</b>  Starting with NDIS 6.30, this function must not be registered for drivers running on low power SoC platforms to avoid negative power impact caused by the periodic <a href="https://docs.microsoft.com/windows-hardware/drivers/network/miniport-adapter-check-for-hang-and-reset-operations">Check-for-Hang</a> activity.</div><div> </div>

## -parameters




### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for a miniport adapter.


## -returns



<i>MiniportCheckForHangEx</i> returns <b>TRUE</b> if the driver determines that a NIC is not
     operating and NDIS should call the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_reset">MiniportResetEx</a> function. For more information, see the Remarks section.




## -remarks



A miniport driver specifies the 
    <i>MiniportCheckForHangEx</i> entry point when it calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
    NdisMRegisterMiniportDriver</a> function.

<i>MiniportCheckForHangEx</i> is not required for intermediate drivers.

<i>MiniportCheckForHangEx</i> does nothing more than check the internal state of the
    NIC and return <b>TRUE</b> if it detects that the NIC is not operating correctly.

By default, NDIS calls 
    <i>MiniportCheckForHangEx</i> approximately every two seconds.  For this reason, your miniport driver's <i>MiniportCheckForHangEx</i> function should return as quickly as possible.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, a coalescable timer with high tolerance is used for measuring intervals between calls to MiniportCheckForHangEx. Therefore this routine should not be used for any time sensitive operations.</div>
<div> </div>
If 
    <i>MiniportCheckForHangEx</i> returns <b>TRUE</b>, NDIS calls the miniport driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_reset">MiniportResetEx</a> function.

If a miniport driver does not complete an OID request within two successive calls to 
    <i>MiniportCheckForHangEx</i>, NDIS can call the driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_reset">MiniportResetEx</a> function. However, to
    avoid unnecessary resets, the driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function can extend the check-for-hang time-out interval
    by setting an appropriate <b>CheckForHangTimeInSeconds</b> value when it calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> function.

For more information about setting the <b>CheckForHangTimeInSeconds</b> time-out value, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/miniport-adapter-check-for-hang-and-reset-operations">Miniport Adapter Check-for-Hang and Reset Operations</a>.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, <i>MiniportCheckForHangEx</i> must return <b>TRUE</b> if the miniport driver detects that the NIC has not completed a pending send request before a time-out period expired. The time-out period is driver-specific, but we recommend using a timeout period of 2 seconds.</div>
<div> </div>
<i>MiniportCheckForHangEx</i> can be preempted by an interrupt.

NDIS calls
    <i>MiniportCheckForHangEx</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportCheckForHangEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportCheckForHangEx</i> function that is named "MyCheckForHangEx", use the <b>MINIPORT_CHECK_FOR_HANG</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_CHECK_FOR_HANG MyCheckForHangEx;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
BOOLEAN
 MyCheckForHangEx(
    NDIS_HANDLE  MiniportAdapterContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_CHECK_FOR_HANG</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_CHECK_FOR_HANG</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/miniport-adapter-check-for-hang-and-reset-operations">Miniport Adapter Check-for-Hang and Reset Operations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_reset">MiniportResetEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
 

 

