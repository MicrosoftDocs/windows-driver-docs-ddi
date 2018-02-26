---
UID: NC:wsk.PFN_WSK_CONTROL_CLIENT
title: PFN_WSK_CONTROL_CLIENT
author: windows-driver-content
description: The WskControlClient function performs control operations on a WSK client object.
old-location: netvista\wskcontrolclient.htm
old-project: netvista
ms.assetid: dad13c60-3511-4641-9182-71a1ce032a69
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PFN_WSK_CONTROL_CLIENT, WskControlClient, WskControlClient callback function [Network Drivers Starting with Windows Vista], netvista.wskcontrolclient, wsk/WskControlClient, wskref_11f754a6-78c0-44ca-8dbc-75521ed659b7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wsk.h
apiname:
-	WskControlClient
product: Windows
targetos: Windows
req.typenames: WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO
req.product: Windows 10 or later.
---

# PFN_WSK_CONTROL_CLIENT callback


## -description


The 
  <b>WskControlClient</b> function performs control operations on a WSK client object.


## -prototype


````
PFN_WSK_CONTROL_CLIENT WskControlClient;

NTSTATUS WSKAPI * WskControlClient(
  _In_      PWSK_CLIENT Client,
  _In_      ULONG       ControlCode,
  _In_      SIZE_T      InputSize,
  _In_opt_  PVOID       InputBuffer,
  _In_      SIZE_T      OutputSize,
  _Out_opt_ PVOID       OutputBuffer,
  _Out_opt_ SIZE_T      *OutputSizeReturned,
  _Inout_   PIRP        Irp
)
{ ... }
````


## -parameters




### -param Client [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a> structure that was returned through
     the 
     <i>WskProviderNpi</i> parameter of the 
     <a href="..\wsk\nf-wsk-wskcaptureprovidernpi.md">
     WskCaptureProviderNPI</a> function.


### -param ControlCode [in]

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
       <a href="https://msdn.microsoft.com/3878053c-388a-4bbc-a30e-feb16eda2f99">TDI</a> transports.



#### WSK_TDI_BEHAVIOR

Control whether the WSK subsystem will divert network I/O to 
       <a href="https://msdn.microsoft.com/3878053c-388a-4bbc-a30e-feb16eda2f99">TDI</a> transports.


### -param InputSize [in]

The number of bytes of data in the buffer that is pointed to by the 
     <i>InputBuffer</i> parameter.


### -param InputBuffer [in, optional]

A caller-allocated buffer that supplies any input data that is required to perform the specified
     control operation. If no input data is required for the specified control operation, the WSK application
     should set this parameter to <b>NULL</b> and set the 
     <i>InputSize</i> parameter to zero.


### -param OutputSize [in]

The size, in bytes, of the buffer that is pointed to by the 
     <i>OutputBuffer</i> parameter.


### -param OutputBuffer [out, optional]

A caller-allocated buffer that receives any output data that is returned by the specified control
     operation. If no output data is returned by the specified control operation, the WSK application should
     set this parameter to <b>NULL</b> and set the 
     <i>OutputSize</i> parameter to zero.


### -param *OutputSizeReturned [out, optional]

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

### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the control operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.
     

This parameter is required, is optional, or must be <b>NULL</b>, depending on the particular client control
     operation that is being performed. For more information about the requirements for this parameter for
     each of the supported client control operations, see 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff571157">WSK Client Control
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
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff571157">WSK Client Control
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
    <a href="https://msdn.microsoft.com/b9d88e59-3c4b-4804-8dd9-02c275927a1e">Windows Filtering
    Platform</a> or 
    <a href="https://msdn.microsoft.com/90264a3d-f002-4205-8e15-9060644117a3">Winsock Kernel</a> instead.</div>
<div> </div>



## -see-also

<a href="..\wsk\nf-wsk-wskcaptureprovidernpi.md">WskCaptureProviderNPI</a>



<a href="..\wsk\ns-wsk-_wsk_provider_npi.md">WSK_PROVIDER_NPI</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff571157">WSK Client Control Operations</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a>



<a href="..\wsk\ns-wsk-_wsk_provider_dispatch.md">WSK_PROVIDER_DISPATCH</a>



<a href="..\wsk\ns-wsk-_wsk_transport.md">WSK_TRANSPORT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_CONTROL_CLIENT callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

