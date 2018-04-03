---
UID: NC:ndis.FILTER_SET_MODULE_OPTIONS
title: FILTER_SET_MODULE_OPTIONS
author: windows-driver-content
description: The FilterSetModuleOptions function changes the set of optional services that are associated with a specified filter module.Note  You must declare the function by using the FILTER_SET_MODULE_OPTIONS type.
old-location: netvista\filtersetmoduleoptions.htm
old-project: netvista
ms.assetid: 04b7ac32-8996-4648-8c88-aa9f630b1bc4
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "(*FILTER_SET_FILTER_MODULE_OPTIONS_HANDLER), (*FILTER_SET_FILTER_MODULE_OPTIONS_HANDLER) callback function [Network Drivers Starting with Windows Vista], FILTER_SET_MODULE_OPTIONS, FilterSetModuleOptions, FilterSetModuleOptions callback function [Network Drivers Starting with Windows Vista], filter_functions_ref_165a2df8-6944-43cc-9e27-711a72e3b160.xml, ndis/FilterSetModuleOptions, netvista.filtersetmoduleoptions"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	(*FILTER_SET_FILTER_MODULE_OPTIONS_HANDLER)
product:
- Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# FILTER_SET_MODULE_OPTIONS callback


## -description


The
  <i>FilterSetModuleOptions</i> function changes the set of optional services that are
  associated with a specified filter module.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_SET_MODULE_OPTIONS</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param FilterModuleContext [in]

A handle to the context area for the filter module that is the target of this request. The filter
     driver created and initialized this context area in the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function.


## -returns



<i>FilterSetModuleOptions</i> returns one of the following status values:

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
<i>FilterSetModuleOptions</i> successfully registered the filter module's optional
       services and resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<i>FilterSetModuleOptions</i> could not allocate the resources that the filter
       module requires.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_
       <i>XXX</i> or NTSTATUS_
       <i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
The filter driver's attempt to register options failed. Usually, such an error status is
       propagated from an 
       <b>Ndis<i>Xxx</i></b> function or a kernel-mode support routine.

</td>
</tr>
</table>
 




## -remarks



If 
    <i>FilterSetModuleOptions</i> is defined, NDIS calls 
    <i>FilterSetModuleOptions</i> before it calls the 
    <a href="https://msdn.microsoft.com/4a917824-eef1-4945-b45e-1c940bc8a50d">FilterRestart</a> function to start the
    filter module.

A filter driver specifies the default values for the changeable filter module options in the
    NDIS_FILTER_DRIVER_CHARACTERISTICS structure that it passes to the 
    <a href="https://msdn.microsoft.com/14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3">
    NdisFRegisterFilterDriver</a> function during driver initialization.

To change options for a specific filter module at run time, the filter driver must also specify an
    entry point for 
    <i>FilterSetModuleOptions</i> in the 
    <a href="https://msdn.microsoft.com/1eb2bae0-70b9-4bc0-9d93-4fc9467f9532">
    NDIS_FILTER_DRIVER_CHARACTERISTICS</a> structure.

To specify the options that should be changed, 
    <i>FilterSetModuleOptions</i> defines a characteristics structure and calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> function.
    Filter drivers must not call 
    <b>NdisSetOptionalHandlers</b> from a different thread.

The possible characteristics structures that can be specified from 
    <i>FilterSetModuleOptions</i> are:


<a href="https://msdn.microsoft.com/4a7f365c-a252-4d8e-bddf-684b3298db5c">
       NDIS_FILTER_PARTIAL_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/66eb9528-e026-44cd-a775-c8d963036adc">
       NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/1925cfd4-f83f-48a5-b928-2c663ac0dc61">
       NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/e80a9999-2e4e-4da0-8aae-54ee71d9249d">
       NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/3eabbad5-b84b-4034-a0b6-d4d515cbc117">
       NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>


For information on the last four structures, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/full-tcp-offload">NDIS 6.0 TCP chimney offload
    documentation</a>.

The options that are specified in each characteristics structure can be different for each filter
    module.

When NDIS calls the 
    <i>FilterDetach</i> function, the filter driver should undo all the operations that
    were performed in 
    <i>FilterSetModuleOptions</i>.

NDIS calls 
    <i>FilterSetModuleOptions</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>FilterSetModuleOptions</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterSetModuleOptions</i> function that is named "MySetModuleOptions", use the <b>FILTER_SET_MODULE_OPTIONS</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FILTER_SET_MODULE_OPTIONS MySetModuleOptions;</pre>
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
 MySetModuleOptions(
    NDIS_HANDLE  FilterModuleContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>FILTER_SET_MODULE_OPTIONS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_SET_MODULE_OPTIONS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/4a917824-eef1-4945-b45e-1c940bc8a50d">FilterRestart</a>



<a href="https://msdn.microsoft.com/1eb2bae0-70b9-4bc0-9d93-4fc9467f9532">
   NDIS_FILTER_DRIVER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/4a7f365c-a252-4d8e-bddf-684b3298db5c">
   NDIS_FILTER_PARTIAL_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>
 

 

