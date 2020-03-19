---
UID: NC:ndis.FILTER_PAUSE
title: FILTER_PAUSE (ndis.h)
description: NDIS calls a filter driver's FilterPause function to initiate a pause operation for the specified filter module.Note  You must declare the function by using the FILTER_PAUSE type.
old-location: netvista\filterpause.htm
tech.root: netvista
ms.assetid: a239889e-ec39-48fc-9e82-c8bc3d7ca51a
ms.date: 05/02/2018
keywords: ["FILTER_PAUSE callback function"]
ms.keywords: FILTER_PAUSE, FILTER_PAUSE callback, FilterPause, FilterPause callback function [Network Drivers Starting with Windows Vista], filter_functions_ref_2f28fa9f-47cb-4638-b673-e938872f54f1.xml, ndis/FilterPause, netvista.filterpause
f1_keywords:
 - "ndis/FilterPause"
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
- FilterPause
product:
- Windows
targetos: Windows
req.typenames: 
---

# FILTER_PAUSE callback function


## -description


NDIS calls a filter driver's 
  <i>FilterPause</i> function to initiate a pause operation for the specified filter module.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_PAUSE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param FilterModuleContext [in]

A handle to the context area for the filter module that the filter driver should pause. The filter
     driver created and initialized this context area in the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.


### -param PauseParameters








#### - FilterPauseParameters [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_pause_parameters">
     NDIS_FILTER_PAUSE_PARAMETERS</a> structure that defines the pause parameters for the filter
     module.


## -returns



NDIS drivers cannot fail a pause request. The filter driver should call the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteeventlogentry">NdisWriteEventLogEntry</a> function
     together with parameters that specify the reason for any errors that occur.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
<i>FilterPause</i> successfully paused the specified filter module.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The filter driver will complete the request asynchronously with a call to the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfpausecomplete">NdisFPauseComplete</a> function.

</td>
</tr>
</table>
 




## -remarks



<i>FilterPause</i> is a required function. NDIS can call 
    <i>FilterPause</i> when the filter module is in the 
    <i>Running</i> state. The filter module enters the 
    <i>Pausing</i> state at the start of execution in the 
    <i>FilterPause</i> function.

A filter driver performs the following operations when NDIS calls 
    <i>FilterPause</i>:

<ul>
<li>
Must call the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfsendnetbufferlistscomplete">
      NdisFSendNetBufferListsComplete</a> function for any queued send buffers that an overlying driver
      created.

</li>
<li>
Must call the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreturnnetbufferlists">
      NdisFReturnNetBufferLists</a> function for any queued receive buffers that an underlying driver
      created.

</li>
<li>
Must wait for NDIS to return all outstanding send requests that the driver originated to the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_send_net_buffer_lists_complete">
      FilterSendNetBufferListsComplete</a> function.

</li>
<li>
Must wait for NDIS to return all outstanding receive indications that the driver originated to the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_return_net_buffer_lists">
      FilterReturnNetBufferLists</a> function.

</li>
</ul>
After the filter driver returns NDIS_STATUS_SUCCESS from 
    <i>FilterPause</i> or calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfpausecomplete">NdisFPauseComplete</a> function, the pause
    operation is complete. The filter module is in the 
    <i>Paused</i> state.

In the 
    <i>Pausing</i> or 
    <i>Paused</i> states, a filter driver should continue to handle OID requests or status indications. The
    driver should reject calls to its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_send_net_buffer_lists">
    FilterSendNetBufferLists</a> function. The driver can pass on calls to its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_receive_net_buffer_lists">
    FilterReceiveNetBufferLists</a> function. However, the driver cannot pass any buffers that it created.
    The driver must not originate any receive indications or send requests.

In the 
    <i>Paused</i> state, the filter module must not generate send requests or receive indications.

NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_restart">FilterRestart</a> function to initiate a
    restart request for a filter module that is in the 
    <i>Paused</i> state.

NDIS calls 
    <i>FilterPause</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>FilterPause</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterPause</i> function that is named "MyPause", use the <b>FILTER_PAUSE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FILTER_PAUSE MyPause;</pre>
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
NDIS_STATUS
 MyPause(
    NDIS_HANDLE  FilterModuleContext,
    PNDIS_FILTER_PAUSE_PARAMETERS  FilterPauseParameters
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>FILTER_PAUSE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_PAUSE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_receive_net_buffer_lists">FilterReceiveNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_restart">FilterRestart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_return_net_buffer_lists">FilterReturnNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_send_net_buffer_lists">FilterSendNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_send_net_buffer_lists_complete">
   FilterSendNetBufferListsComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_pause_parameters">NDIS_FILTER_PAUSE_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfpausecomplete">NdisFPauseComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreturnnetbufferlists">NdisFReturnNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfsendnetbufferlistscomplete">
   NdisFSendNetBufferListsComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteeventlogentry">NdisWriteEventLogEntry</a>
 

 

