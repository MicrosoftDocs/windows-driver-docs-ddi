---
UID: NC:ndis.MINIPORT_PNP_IRP
title: MINIPORT_PNP_IRP (ndis.h)
description: The MiniportPnpIrp function enables a miniport driver to optionally manage its Plug and Play (PnP) resources.
old-location: netvista\miniportstartdevice.htm
tech.root: netvista
ms.assetid: ccccb2c5-16ba-4463-bb35-1dc3dcc61a2f
ms.date: 05/02/2018
keywords: ["MINIPORT_PNP_IRP callback function"]
ms.keywords: "(*MINIPORT_PNP_IRP_HANDLER), (*MINIPORT_PNP_IRP_HANDLER) callback function [Network Drivers Starting with Windows Vista], MINIPORT_PNP_IRP, MINIPORT_PNP_IRP callback, MiniportPnpIrp, MiniportPnpIrp callback function [Network Drivers Starting with Windows Vista], ndis/MiniportPnpIrp, ndis_msix_ref_421866fc-9921-4101-87b5-3d48e064f855.xml, netvista.miniportstartdevice"
f1_keywords:
 - "ndis/(*MINIPORT_PNP_IRP_HANDLER)"
 - "(*MINIPORT_PNP_IRP_HANDLER)"
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
- (*MINIPORT_PNP_IRP_HANDLER)
targetos: Windows
req.typenames: 
---

# MINIPORT_PNP_IRP callback function


## -description


The <i>MiniportPnpIrp</i> function enables a miniport driver to optionally manage its Plug and Play (PnP) resources. <i>
   MiniportPnpIrp</i> itself is never defined by miniport drivers directly. Instead, it is defined either as <i>
   MiniportFilterResourceRequirements</i> or <i>MiniportStartDevice</i>.

 If defined as <i>
   MiniportFilterResourceRequirements</i>, this function enables a miniport driver to modify
   the resource requirements for a device. If defined as  <i>MiniportStartDevice</i>, this function enables the miniport driver to remove resources that it added in the 
   <i>
   MiniportFilterResourceRequirements</i> function.
<div class="alert"><b>Note</b>  You must declare this function by using the either the <b>MINIPORT_FILTER_RESOURCE_REQUIREMENTS</b> type or the <b>MINIPORT_START_DEVICE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportAddDeviceContext [in]

A handle for a driver-allocated context area that the miniport driver registered with NDIS in the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_add_device">MiniportAddDevice</a> function.


### -param Irp [in]

If this function is defined as <i>
   MiniportFilterResourceRequirements</i>, this parameter is a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-filter-resource-requirements">
     IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a> for the driver to handle.

If this function is defined as <i>MiniportStartDevice</i>, this parameter is a pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a> IRP.


## -returns



<i>MiniportPnpIrp</i> returns one of the following values:

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
The miniport driver handled the start device request successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver could not handle the start device request because of low resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
<i>MiniportFilterResourceRequirements</i> failed for reasons other than
       insufficient resources.

</td>
</tr>
</table>
 




## -remarks



<h3><a id="MiniportFilterResourceRequirements_Remarks"></a><a id="miniportfilterresourcerequirements_remarks"></a><a id="MINIPORTFILTERRESOURCEREQUIREMENTS_REMARKS"></a>MiniportFilterResourceRequirements Remarks</h3>
The 
    <i>MiniportFilterResourceRequirements</i> function is an optional function. Miniport
    drivers should register this function if they support MSI-X and at least one of the following is
    true:

<ul>
<li>
The driver requires the ability to change the interrupt affinity for each MSI-X message.

</li>
<li>
The driver will register for line-based interrupts in the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
      MiniportInitializeEx</a> function.

</li>
</ul>
To register 
    <i>MiniportFilterResourceRequirements</i>, specify the entry point in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_pnp_characteristics">
    NDIS_MINIPORT_PNP_CHARACTERISTICS</a> structure.

NDIS calls the 
    <i>MiniportFilterResourceRequirements</i> function after NDIS receives an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-filter-resource-requirements">
    IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a> IRP for a network interface card (NIC). NDIS calls 
    <i>MiniportFilterResourceRequirements</i> after the underlying function drivers in the
    device stack have completed the processing of the IRP.

The miniport driver must be prepared to handle IRP_MN_FILTER_RESOURCE_REQUIREMENTS from 
    <i>MiniportFilterResourceRequirements</i> immediately after the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_add_device">MiniportAddDevice</a> function returns
    NDIS_STATUS_SUCCESS.

A miniport driver can set an affinity policy for each resource of type 
    <b>CmResourceTypeInterrupt</b> that describes an MSI-X message. If an affinity policy requests targeting
    for a specific set of processors, the miniport driver also sets a 
    [**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity) mask at the 
    <b>Interrupt.TargetedProcessors</b> member in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a> structure.

If an NDIS 6.1 or later miniport driver requires more message interrupt resources, it can add more
    message interrupt resources to the resources list. If the operating system can provide more message
    interrupt resources, the miniport adapter receives the added message interrupt resources when it is
    started.

Each message interrupt resource in the list is assigned a message number that corresponds to the order
    it has in the resource list. The messages are numbered from 0 through the total number of message
    interrupt resources minus one.

To assign an MSI-X table entry to a CPU at run time, the miniport driver can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismconfigmsixtableentry">
    NdisMConfigMSIXTableEntry</a> function.

A miniport driver can remove all of the resources of type 
    <b>CmResourceTypeInterrupt</b> that are message interrupt resources. The driver can then register for
    line-based interrupts in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function. If
    the miniport driver does not remove these message interrupt resources, the operating system will fail if
    the driver tries to register line-based interrupt in 
    <i>MiniportInitializeEx</i>.

To allocate memory for a new resource-requirements list, use the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatememorywithtagpriority">
    NdisAllocateMemoryWithTagPriority</a> function. The miniport driver can free the memory for the old
    resources-requirement list with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreememory">NdisFreeMemory</a> function. The PnP manager
    frees any driver-allocated memory after the associated IRP is complete.

Miniport drivers should not modify other resources, such as 
    <b>CmResourceTypeMemory</b> and 
    <b>CmResourceTypePort</b> resources. Miniport drivers should avoid adding a new resource to the resource
    list. However, miniport drivers can add more message interrupt resources. If the miniport driver adds
    more message interrupt resources, the driver must not remove them from the 
    <i>MiniportStartDevice</i> function.

If a miniport driver returns NDIS_STATUS_RESOURCES or NDIS_STATUS_FAILURE from <i>MiniportFilterResourceRequirements</i>, NDIS will use the resource requirements as specified by the parent bus driver.

NDIS can call 
    <i>MiniportFilterResourceRequirements</i> several times before NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_remove_device">MiniportRemoveDevice</a> function. But
    NDIS calls 
    <i>MiniportFilterResourceRequirements</i> only when a device is in the halted
    state.

NDIS calls 
    <i>MiniportFilterResourceRequirements</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="MiniportFilterResourceRequirements_Example"></a><a id="miniportfilterresourcerequirements_example"></a><a id="MINIPORTFILTERRESOURCEREQUIREMENTS_EXAMPLE"></a>MiniportFilterResourceRequirements Example</h3>
To define a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pnp_irp">MiniportFilterResourceRequirements</a> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pnp_irp">MiniportFilterResourceRequirements</a> function that is named "MyFilterResourceRequirements", use the <b>MINIPORT_FILTER_RESOURCE_REQUIREMENTS</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_FILTER_RESOURCE_REQUIREMENTS MyFilterResourceRequirements;</pre>
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
 MyFilterResourceRequirements(
    NDIS_HANDLE  MiniportAddDeviceContext,
    PIRP  Irp
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_FILTER_RESOURCE_REQUIREMENTS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_FILTER_RESOURCE_REQUIREMENTS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 

<h3><a id="MiniportStartDevice_Remarks"></a><a id="miniportstartdevice_remarks"></a><a id="MINIPORTSTARTDEVICE_REMARKS"></a>MiniportStartDevice Remarks</h3>
<i>MiniportStartDevice</i> is an optional function. Miniport drivers that support
    MSI-X can specify an entry point for this function in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_pnp_characteristics">
    NDIS_MINIPORT_PNP_CHARACTERISTICS</a> structure. When NDIS receives a request from the Plug and Play
    (PnP) manager to start a device, NDIS calls the 
    <i>MiniportStartDevice</i> function, if any. If a miniport driver adds new resources
    in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pnp_irp">
    MiniportFilterResourceRequirements</a> function, it should provide a 
    <i>MiniportStartDevice</i> function to remove the resources.

If a miniport driver modifies resources in such a way that an underlying bus driver cannot recognize
    the resources, the driver should provide a 
    <i>MiniportStartDevice</i> function to remove the resources. An underlying bus driver
    might fail a start device request if it does not recognize resources that a miniport driver added in 
    <i>MiniportFilterResourceRequirements</i>. If the miniport driver adds message
    interrupt resources, it must not remove them from 
    <i>MiniportStartDevice</i>.

NDIS calls 
    <i>MiniportStartDevice</i> before it forwards the start device request to the
    underlying drivers. If an underlying driver successfully completes the request, NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function to
    initialize the miniport adapter.

NDIS calls 
    <i>MiniportStartDevice</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="MiniportStartDevice_Example"></a><a id="miniportstartdevice_example"></a><a id="MINIPORTSTARTDEVICE_EXAMPLE"></a>MiniportStartDevice Example</h3>
To define a <i>MiniportStartDevice</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportStartDevice</i> function that is named "MyStartDevice", use the <b>MINIPORT_START_DEVICE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_START_DEVICE MyStartDevice;</pre>
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
 MyStartDevice(
    NDIS_HANDLE  MiniportAddDeviceContext,
    PIRP  Irp
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_START_DEVICE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_START_DEVICE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-filter-resource-requirements">
   IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a>



[**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity)



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_add_device">MiniportAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pnp_irp">
   MiniportFilterResourceRequirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_remove_device">MiniportRemoveDevice</a>



<b>MiniportStartDevice</b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_pnp_characteristics">
   NDIS_MINIPORT_PNP_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatememorywithtagpriority">
   NdisAllocateMemoryWithTagPriority</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreememory">NdisFreeMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismconfigmsixtableentry">NdisMConfigMSIXTableEntry</a>
 

 

