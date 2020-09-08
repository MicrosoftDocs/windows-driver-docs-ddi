---
UID: NC:wsk.PFN_WSK_CONTROL_CLIENT
title: PFN_WSK_CONTROL_CLIENT (wsk.h)
description: The WskControlClient function performs control operations on a WSK client object.
old-location: netvista\wskcontrolclient.htm
tech.root: netvista
ms.assetid: dad13c60-3511-4641-9182-71a1ce032a69
ms.date: 05/02/2018
keywords: ["PFN_WSK_CONTROL_CLIENT callback function"]
ms.keywords: PFN_WSK_CONTROL_CLIENT, PFN_WSK_CONTROL_CLIENT callback, WskControlClient, WskControlClient callback function [Network Drivers Starting with Windows Vista], netvista.wskcontrolclient, wsk/WskControlClient, wskref_11f754a6-78c0-44ca-8dbc-75521ed659b7.xml
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PFN_WSK_CONTROL_CLIENT
 - wsk/PFN_WSK_CONTROL_CLIENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wsk.h
api_name:
 - WskControlClient
---

# PFN_WSK_CONTROL_CLIENT callback function


## -description

The 
  <b>WskControlClient</b> function performs control operations on a WSK client object.

## -parameters

### -param Client 

[in]
A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wsk-client">WSK_CLIENT</a> structure that was returned through
     the 
     <i>WskProviderNpi</i> parameter of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskcaptureprovidernpi">
     WskCaptureProviderNPI</a> function.

### -param ControlCode 

[in]
The control operation that is being performed. A WSK application can specify one of the following
     control codes:
     





#### WSK_TRANSPORT_LIST_QUERY

Retrieve a list of available network transports.



#### WSK_TRANSPORT_LIST_CHANGE

Receive notification of a change to the list of available network transports.



#### WSK_CACHE_SD

Obtain a cached copy of a security descriptor.



#### WSK_RELEASE_SD

Release a cached copy of a security descriptor.



#### WSK_SET_STATIC_EVENT_CALLBACKS

Enable specified event callback functions automatically on all sockets.



#### WSK_TDI_DEVICENAME_MAPPING

Map combinations of address family, socket type, and protocol to device names of 
       <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff565094(v=vs.85)">TDI</a> transports.



#### WSK_TDI_BEHAVIOR

Control whether the WSK subsystem will divert network I/O to 
       <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff565094(v=vs.85)">TDI</a> transports.

### -param InputSize 

[in]
The number of bytes of data in the buffer that is pointed to by the 
     <i>InputBuffer</i> parameter.

### -param InputBuffer 

[in, optional]
A caller-allocated buffer that supplies any input data that is required to perform the specified
     control operation. If no input data is required for the specified control operation, the WSK application
     should set this parameter to <b>NULL</b> and set the 
     <i>InputSize</i> parameter to zero.

### -param OutputSize 

[in]
The size, in bytes, of the buffer that is pointed to by the 
     <i>OutputBuffer</i> parameter.

### -param OutputBuffer 

[out, optional]
A caller-allocated buffer that receives any output data that is returned by the specified control
     operation. If no output data is returned by the specified control operation, the WSK application should
     set this parameter to <b>NULL</b> and set the 
     <i>OutputSize</i> parameter to zero.

### -param OutputSizeReturned 

[out, optional]
A pointer to a ULONG-typed variable that receives the number of bytes of data that is returned in
     the buffer that is pointed to by the 
     <i>OutputBuffer</i> parameter. A WSK application should set this pointer to <b>NULL</b> except when all of the
     following are true:
     

<ul>
<li>
The 
       <i>Irp</i> parameter is <b>NULL</b>.

</li>
<li>
The operation that is being performed returns output data in the buffer that is pointed to by the 
       <i>OutputBuffer</i> parameter.

</li>
<li>
The number of bytes of output data that is returned by the operation that is being performed is
       unknown.

</li>
</ul>

### -param Irp 

[in, out]
A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the control operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.
     

This parameter is required, is optional, or must be <b>NULL</b>, depending on the particular client control
     operation that is being performed. For more information about the requirements for this parameter for
     each of the supported client control operations, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wsk-client-control-operations">WSK Client Control
     Operations</a>.

## -returns

<b>WskControlClient</b> returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The control operation completed successfully. If the WSK application specified a pointer to an
       IRP in the 
       <i>Irp</i> parameter, the IRP will be completed with success status.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not complete the control operation immediately. The WSK subsystem will
       complete the IRP after it has completed the control operation. The status of the control operation
       will be returned in the 
       <b>IoStatus.Status</b> field of the IRP.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The output buffer is not large enough to contain the returned data. The variable that is pointed
       to by the 
       <i>OutputSizeReturned</i> parameter contains the required buffer size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. The IRP will be completed with failure status.

</td>
</tr>
</table>

## -remarks

For more information about how the input and output buffers are used for each client control
    operation, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wsk-client-control-operations">WSK Client Control
    Operations</a>.

If the 
    <b>WskControlClient</b> function returns STATUS_PENDING, any buffers that are pointed to by the 
    <i>InputBuffer</i> parameter or the 
    <i>OutputBuffer</i> parameter must remain valid until the IRP is completed. If the WSK application
    allocated the buffers with one of the 
    <b>ExAllocate<i>Xxx</i></b> functions, it cannot free the memory with the corresponding 
    <b>ExFree<i>Xxx</i></b> function until after the IRP is completed. If the WSK application allocated the buffers on the
    stack, it cannot return from the function that calls the 
    <b>WskControlClient</b> function until after the IRP is completed.

<div class="alert"><b>Note</b>  TDI will not be supported in Microsoft Windows versions after Windows Vista. Use 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">Windows Filtering
    Platform</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">Winsock Kernel</a> instead.</div>
<div> </div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wsk-client-control-operations">WSK Client Control Operations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wsk-client">WSK_CLIENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_dispatch">WSK_PROVIDER_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_npi">WSK_PROVIDER_NPI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_transport">WSK_TRANSPORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskcaptureprovidernpi">WskCaptureProviderNPI</a>

