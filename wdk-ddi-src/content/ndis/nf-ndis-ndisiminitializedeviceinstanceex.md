---
UID: NF:ndis.NdisIMInitializeDeviceInstanceEx
title: NdisIMInitializeDeviceInstanceEx function (ndis.h)
description: The NdisIMInitializeDeviceInstanceEx function initiates the initialization operation for a virtual miniport and optionally sets up state information about the virtual miniport for subsequently bound protocol drivers.
old-location: netvista\ndisiminitializedeviceinstanceex.htm
tech.root: netvista
ms.assetid: f65c2974-4bf4-4948-ac07-527e69c96303
ms.date: 05/02/2018
keywords: ["NdisIMInitializeDeviceInstanceEx function"]
ms.keywords: NdisIMInitializeDeviceInstanceEx, NdisIMInitializeDeviceInstanceEx function [Network Drivers Starting with Windows Vista], intermediate_ref_37fbd7e8-287e-49dc-8de5-6b438a305804.xml, ndis/NdisIMInitializeDeviceInstanceEx, netvista.ndisiminitializedeviceinstanceex
f1_keywords:
 - "ndis/NdisIMInitializeDeviceInstanceEx"
 - "NdisIMInitializeDeviceInstanceEx"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisIMInitializeDeviceInstanceEx (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisIMInitializeDeviceInstanceEx (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_IM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisIMInitializeDeviceInstanceEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisIMInitializeDeviceInstanceEx function


## -description


The
  <b>NdisIMInitializeDeviceInstanceEx</b> function initiates the initialization operation for a virtual
  miniport and optionally sets up state information about the virtual miniport for subsequently bound
  protocol drivers.


## -parameters




### -param DriverHandle [in]

The miniport driver handle that the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a> function returns at 
     <i>NdisMiniportDriverHandle</i> .


### -param DriverInstance [in]

A pointer to an NDIS_STRING type that describes a caller-initialized counted string in the
     system-default character set. The string contains the name of the registry key in which the driver
     stores information about a virtual miniport and, possibly, binding-specific information. For Microsoft
     Windows 2000 and later drivers, this string contains Unicode characters. That is, for Windows 2000 and
     later, NDIS defines the NDIS_STRING type as a 
     <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> type.


### -param DeviceContext [in, optional]

A pointer to caller-supplied memory to be set up with driver-defined device context information
     about the virtual miniport, which still higher level protocol drivers that subsequently bind themselves
     to this virtual miniport can use. This parameter can be <b>NULL</b> if the intermediate driver has no such
     device context area.


## -returns



<b>NdisIMInitializeDeviceInstanceEx</b> can return either of the following:

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
NDIS initiated the initialization operation for the intermediate driver's virtual
       miniport.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisIMInitializeDeviceInstanceEx</b> failed because the device specified by 
       <i>DriverHandle</i> has already been initialized.

</td>
</tr>
</table>
 




## -remarks



An NDIS intermediate driver should call 
    <b>NdisIMInitializeDeviceInstanceEx</b> from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a> function. A
    failure to call 
    <b>NdisIMInitializeDeviceInstanceEx</b> from an NDIS intermediate driver effectively prevents that driver
    from loading successfully.

Before it calls 
    <b>NdisIMInitializeDeviceInstanceEx</b>, the intermediate driver's 
    <i>ProtocolBindAdapterEx</i> function should bind to any underlying miniport drivers that are required for
    the intermediate driver to function. The 
    <i>ProtocolBindAdapterEx</i> function can allocate an area at 
    <i>DeviceContext</i> as well, possibly setting it up with intermediate driver-determined information about
    the capabilities of the underlying miniport adapter and that was collected by 
    <i>ProtocolBindAdapterEx</i>. The intermediate driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function
    might use such information subsequently to set up this context area with information about the driver's
    virtual miniport.

The intermediate driver's call to 
    <b>NdisIMInitializeDeviceInstanceEx</b> causes NDIS to call the intermediate driver's 
    <i>MiniportInitializeEx</i> function, if NDIS receives an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a> IRP to start the device.
    If NDIS does not receive such an IRP, NDIS will not call the intermediate driver's 
    <i>MiniportInitializeEx</i> function.

The call to 
    <i>MiniportInitializeEx</i> can happen at a later time and therefore is not necessarily within the context
    of the call to 
    <b>NdisIMInitializeDeviceInstanceEx</b>. If NDIS never calls 
    <i>MiniportInitializeEx</i> for the virtual miniport that is referenced in a call to 
    <b>NdisIMInitializeDeviceInstanceEx</b> and the intermediate driver no longer requires the virtual
    miniport, the intermediate driver should call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisimcancelinitializedeviceinstance">
    NdisIMCancelInitializeDeviceInstance</a> function to cancel the initialization of the virtual miniport.
    For example, suppose that an intermediate driver creates a virtual miniport in response to a successful
    binding to an underlying miniport adapter. If that binding is removed before NDIS calls 
    <i>MiniportInitializeEx</i>, the intermediate driver should call 
    <b>NdisIMCancelInitializeDeviceInstance</b> to cancel the initialization of the virtual miniport.

<i>MiniportInitializeEx</i> allocates any resources that the driver requires to carry out network I/O
    operations, such as calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> function, and to initialize the driver's virtual miniport to an
    operational state. Then, higher-level protocol drivers can bind themselves to its virtual miniport when
    the intermediate driver's initialization is completed successfully.

After 
    <i>MiniportInitializeEx</i> returns control, the intermediate driver's device context area, if any, can
    contain any intermediate-driver-defined data that subsequently enables all higher-level protocol drivers
    that are bound to the same virtual miniport to access information in that context area. Such a
    higher-level protocol driver can query the intermediate-driver-supplied device context with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisimgetbindingcontext">
    NdisIMGetBindingContext</a> function.

Before NDIS calls an intermediate driver's 
    <i>MiniportInitializeEx</i> function, the driver can call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisimcancelinitializedeviceinstance">
    NdisIMCancelInitializeDeviceInstance</a> to cancel the initialization operation.

After NDIS calls an intermediate driver's 
    <i>MiniportInitializeEx</i> function, the driver must call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisimdeinitializedeviceinstance">
    NdisIMDeInitializeDeviceInstance</a> to reverse the initialization operation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatememorywithtagpriority">
   NdisAllocateMemoryWithTagPriority</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisimcancelinitializedeviceinstance">
   NdisIMCancelInitializeDeviceInstance</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisimdeinitializedeviceinstance">
   NdisIMDeInitializeDeviceInstance</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisimgetbindingcontext">NdisIMGetBindingContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisiminitializedeviceinstanceex">
   NdisIMInitializeDeviceInstanceEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializestring">NdisInitializeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

