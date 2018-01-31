---
UID: NC:ndis.MINIPORT_RESTART
title: MINIPORT_RESTART
author: windows-driver-content
description: The MiniportRestart function initiates a restart request for a miniport adapter that is paused.
old-location: netvista\miniportrestart.htm
old-project: netvista
ms.assetid: 31a18040-2c66-4074-9ace-dd604b4bfe22
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportrestart, MiniportRestart callback function [Network Drivers Starting with Windows Vista], MiniportRestart, MINIPORT_RESTART, MINIPORT_RESTART, ndis/MiniportRestart, miniport_functions_ref_3ab5d6bf-6192-4c9b-af88-a5dd0efe4d37.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndis.h
apiname:
-	MiniportRestart
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MINIPORT_RESTART callback


## -description


The 
   <i>MiniportRestart</i> function initiates a restart request for a miniport adapter that
   is paused.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_RESTART</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_RESTART MiniportRestart;

NDIS_STATUS MiniportRestart(
  _In_ NDIS_HANDLE                       MiniportAdapterContext,
  _In_ PNDIS_MINIPORT_RESTART_PARAMETERS MiniportRestartParameters
)
{ ... }
````


## -parameters




#### - MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for a miniport adapter.


### -param RestartParameters






#### - MiniportRestartParameters [in]

A pointer to an 
     <mshelp:link keywords="netvista.ndis_miniport_restart_parameters" tabindex="0"><b>
     NDIS_MINIPORT_RESTART_PARAMETERS</b></mshelp:link> structure that defines the restart parameters for the miniport
     adapter.


## -returns


<i>MiniportRestart</i> returns one of the following status values:
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

<a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a> successfully restarted the flow of network data through the
       miniport adapter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
<i>MiniportRestart</i> did not complete the restart operation and the operation
       will be completed asynchronously. The miniport driver must call the 
       <a href="..\ndis\nf-ndis-ndismrestartcomplete.md">NdisMRestartComplete</a> function when
       the operation is complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a> failed because of insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
None of the preceding status values applies. In this situation, the driver should call the 
       <a href="..\ndis\nf-ndis-ndiswriteerrorlogentry.md">NdisWriteErrorLogEntry</a> function
       with parameters that specify the reason for the failure.

</td>
</tr>
</table> 



## -remarks


A driver specifies the 
    <i>MiniportRestart</i> entry point when it calls the 
    <mshelp:link keywords="netvista.ndismregisterminiportdriver" tabindex="0"><b>
    NdisMRegisterMiniportDriver</b></mshelp:link> function.

The miniport adapter that is specified by the 
    <i>MiniportAdapterContext</i> parameter enters the 
    <i>Restarting</i> state when NDIS calls 
    <i>MiniportRestart</i>.

When NDIS calls 
    <i>MiniportRestart</i>, a miniport driver:
<ul>
<li>
Must complete any tasks that are required to resume send and receive operations.

</li>
<li>
Optionally modifies the restart attributes that are specified in the 
      <b>RestartAttributes</b> member of the 
      <mshelp:link keywords="netvista.ndis_miniport_restart_parameters" tabindex="0"><b>
      NDIS_MINIPORT_RESTART_PARAMETERS</b></mshelp:link> structure. If the pointer in 
      <b>RestartAttributes</b> is <b>NULL</b>, the miniport driver should not modify or add to the restart attributes
      list. If the pointer in 
      <b>RestartAttributes</b> is non-<b>NULL</b>, it points to an 
      <a href="..\ndis\ns-ndis-_ndis_restart_attributes.md">NDIS_RESTART_ATTRIBUTES</a> structure.
      If a miniport driver does not restart, it should not modify any attributes.

</li>
<li>
Can provide status indications with the 
      <mshelp:link keywords="netvista.ndismindicatestatusex" tabindex="0"><b>
      NdisMIndicateStatusEx</b></mshelp:link> function.

</li>
<li>
Should handle status requests in the 
      <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.

</li>
</ul>If a miniport driver modifies the list of restart attributes, the miniport driver:
<ul>
<li>
Can add new media-specific attributes to the list of restart attributes. In this situation, the
      miniport driver must allocate a new 
      <mshelp:link keywords="netvista.ndis_restart_attributes" tabindex="0"><b>
      NDIS_RESTART_ATTRIBUTES</b></mshelp:link> structure--for example, with the 
      <mshelp:link keywords="netvista.ndisallocatememorywithtagpriority" tabindex="0"><b>
      NdisAllocateMemoryWithTagPriority</b></mshelp:link> function--and provide memory space for the new attributes.
      After propagating the restart attributes to overlying drivers, NDIS frees the attributes memory for the
      miniport drivers.

</li>
<li>
Can modify the media-specific attributes in the list of restart attributes. If the miniport driver
      requires more memory space, it can free an NDIS_RESTART_ATTRIBUTES structure with the 
      <a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a> function and allocate a
      new structure to contain the modified information. After propagating the restart attributes to
      overlying drivers, NDIS frees the attributes memory for the miniport drivers.

</li>
<li>
Can modify any field in the 
      <mshelp:link keywords="netvista.ndis_restart_general_attributes" tabindex="0"><b>
      NDIS_RESTART_GENERAL_ATTRIBUTES</b></mshelp:link> structure. When NDIS provides a non-<b>NULL</b> pointer in the 
      <b>RestartAttributes</b> member of the 
      <mshelp:link keywords="netvista.ndis_miniport_restart_parameters" tabindex="0"><b>
      NDIS_MINIPORT_RESTART_PARAMETERS</b></mshelp:link> structure, the attributes list contains one entry in which the 
      <b>Oid</b> member in the 
      <a href="..\ndis\ns-ndis-_ndis_restart_attributes.md">NDIS_RESTART_ATTRIBUTES</a> structure
      is 
      <mshelp:link keywords="netvista.oid_gen_miniport_restart_attributes" tabindex="0">
      OID_GEN_MINIPORT_RESTART_ATTRIBUTES</mshelp:link> and the 
      <b>Data</b> member contains an NDIS_RESTART_GENERAL_ATTRIBUTES structure.

</li>
<li>
Should make sure that the 
      <mshelp:link keywords="netvista.ndis_restart_general_attributes" tabindex="0"><b>
      NDIS_RESTART_GENERAL_ATTRIBUTES</b></mshelp:link> structure contains the correct information. To make sure that the
      NDIS_RESTART_GENERAL_ATTRIBUTES structure contains the required information, you should first determine
      the version of the structure by checking the 
      <b>Revision</b> member in the 
      <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure that is
      specified in the 
      <b>Header</b> member of the NDIS_RESTART_GENERAL_ATTRIBUTES structure.

</li>
</ul>NDIS does not initiate other Plug and Play (PnP) operations for the miniport adapter, such as halt,
    initialize, power change, or a pause request, until the restart operation is complete.

After the miniport driver successfully restarts the send and receive operations, it must complete the
    restart operation. If the driver returns NDIS_STATUS_SUCCESS from 
    <i>MiniportRestart</i>, the restart operation is complete. If the driver returns
    NDIS_STATUS_PENDING, it can continue restart operations. The restart operation is complete after the
    driver calls the 
    <a href="..\ndis\nf-ndis-ndismrestartcomplete.md">NdisMRestartComplete</a> function. After
    the restart operation is complete, the miniport adapter is in the 
    <i>Running</i> state.

The miniport driver can resume indicating received packets for the miniport adapter immediately after
    NDIS calls 
    <i>MiniportRestart</i> and before the driver calls 
    <b>NdisMRestartComplete</b>. The miniport driver should be ready to accept send requests after the driver
    completes the restart request.

If the miniport driver does not restart the send and receive operations, the driver must return an
    appropriate failure status from 
    <i>MiniportRestart</i>. In this situation, the driver must stop any send or receive
    operations that were started and then return to the 
    <i>Paused</i> state.

NDIS calls 
    <i>MiniportRestart</i> at IRQL = PASSIVE_LEVEL.
<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>To define a <i>MiniportRestart</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportRestart</i> function that is named "MyRestart", use the <b>MINIPORT_RESTART</b> type as shown in this code example:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_RESTART MyRestart;</pre>
</td>
</tr>
</table></span></div>Then, implement your function as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NDIS_STATUS
 MyRestart(
    NDIS_HANDLE  MiniportAdapterContext,
    PNDIS_MINIPORT_RESTART_PARAMETERS  RestartParameters
    )
  {...}</pre>
</td>
</tr>
</table></span></div>The <b>MINIPORT_RESTART</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_RESTART</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 



## -see-also

<mshelp:link keywords="netvista.oid_gen_miniport_restart_attributes" tabindex="0">
   OID_GEN_MINIPORT_RESTART_ATTRIBUTES</mshelp:link>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<mshelp:link keywords="netvista.ndis_miniport_restart_parameters" tabindex="0"><b>
   NDIS_MINIPORT_RESTART_PARAMETERS</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndismrestartcomplete.md">NdisMRestartComplete</a>

<a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a>

<mshelp:link keywords="netvista.ndisallocatememorywithtagpriority" tabindex="0"><b>
   NdisAllocateMemoryWithTagPriority</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndiswriteerrorlogentry.md">NdisWriteErrorLogEntry</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a>

<a href="..\ndis\ns-ndis-_ndis_restart_attributes.md">NDIS_RESTART_ATTRIBUTES</a>

<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>

<a href="..\ndis\nc-ndis-miniport_pause.md">MiniportPause</a>

<mshelp:link keywords="netvista.ndis_restart_general_attributes" tabindex="0"><b>
   NDIS_RESTART_GENERAL_ATTRIBUTES</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndismindicatestatusex.md">NdisMIndicateStatusEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_RESTART callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

