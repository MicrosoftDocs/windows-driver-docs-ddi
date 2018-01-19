---
UID: NC:wsk.PFN_WSK_CONTROL_SOCKET
title: PFN_WSK_CONTROL_SOCKET
author: windows-driver-content
description: The WskControlSocket function performs control operations on a socket.
old-location: netvista\wskcontrolsocket.htm
old-project: netvista
ms.assetid: d65fd2ab-ffca-4e13-b0f1-42d6a89f4b4a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO, WPP_TRIAGE_INFO
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
req.alt-api: WskControlSocket
req.alt-loc: wsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL (see Remarks section)
req.typenames: *PWPP_TRIAGE_INFO, WPP_TRIAGE_INFO
req.product: Windows 10 or later.
---

# PFN_WSK_CONTROL_SOCKET callback



## -description
The 
  <b>WskControlSocket</b> function performs control operations on a socket.



## -prototype

````
PFN_WSK_CONTROL_SOCKET WskControlSocket;

NTSTATUS WSKAPI * WskControlSocket(
  _In_      PWSK_SOCKET             Socket,
  _In_      WSK_CONTROL_SOCKET_TYPE RequestType,
  _In_      ULONG                   ControlCode,
  _In_      ULONG                   Level,
  _In_      SIZE_T                  InputSize,
  _In_opt_  PVOID                   InputBuffer,
  _In_      SIZE_T                  OutputSize,
  _Out_opt_ PVOID                   OutputBuffer,
  _Out_opt_ SIZE_T                  *OutputSizeReturned,
  _Inout_   PIRP                    Irp
)
{ ... }
````


## -parameters

### -param Socket [in]

A pointer to a 
     <a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a> structure that specifies the socket
     object for the socket on which the control operation is being performed.


### -param RequestType [in]

A value that specifies the type of control operation that is being performed. A WSK application
     sets this parameter to one of the following values:
     




### -param WskSetOption

Set the state or value for a socket option.


### -param WskGetOption

Get the state or value of a socket option.


### -param WskIoctl

Perform an I/O control operation.

</dd>
</dl>

### -param ControlCode [in]

If the 
     <i>RequestType</i> parameter is set to 
     <b>WskSetOption</b> or 
     <b>WskGetOption</b>, the 
     <i>ControlCode</i> parameter specifies the particular socket option whose value is being set or
     retrieved. For more information about socket options that are supported by the WSK subsystem, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571186">WSK Socket Options</a>. The underlying
     network protocol might support additional socket options.
     

If the 
     <i>RequestType</i> parameter is set to 
     <b>WskIoctl</b>, the 
     <i>ControlCode</i> parameter specifies the particular I/O control operation that is being performed. For
     more information about I/O control operations that are supported by the WSK subsystem, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/wsk-socket-ioctl-operations">WSK Socket IOCTL Operations</a>. The
     underlying network protocol might support additional socket I/O control operations.


### -param Level [in]

The level in the network stack at which the value for a socket option is being either set or
     retrieved. For WSK subsystem level socket options, the WSK application should set this parameter to
     SOL_SOCKET. For transport protocol or network protocol level socket options, the WSK application should
     set this parameter to the appropriate level for the underlying transport.
     

If the 
     <i>RequestType</i> parameter is set to 
     <b>WskIoctl</b>, the 
     <i>Level</i> parameter is ignored.


### -param InputSize [in]

The number of bytes of data in the buffer that is pointed to by the 
     <i>InputBuffer</i> parameter.


### -param InputBuffer [in, optional]

A caller-allocated buffer that supplies any input data that is required to perform the specified
     control operation. If no input data is required for the specified control operation, the WSK application
     should set this parameter to <b>NULL</b> and set the 
     <i>InputSize</i> parameter to zero.


### -param OutputSize [in]

The size of the buffer that is pointed to by the 
     <i>OutputBuffer</i> parameter.


### -param OutputBuffer [out, optional]

A caller-allocated buffer that receives any output data that is returned by the specified control
     operation. If no output data is returned by the specified control operation, the WSK application should
     set this parameter to <b>NULL</b> and set the 
     <i>OutputSize</i> parameter to zero.


### -param OutputSizeReturned [out, optional]

A pointer to a ULONG-typed variable that receives the number of bytes of data that is returned in
     the buffer that is pointed to by the 
     <i>OutputBuffer</i> parameter. A WSK application should set the 
     <i>OutputSizeReturned</i> parameter to <b>NULL</b> except when all of the following are true:
     

<ul>
<li>
The 
       <i>Irp</i> parameter is set to <b>NULL</b>.

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
     

If the 
     <i>RequestType</i> parameter is set to either 
     <b>WskSetOption</b> or 
     <b>WskGetOption</b>, the 
     <i>Irp</i> parameter is required, is optional, or must be <b>NULL</b> depending on the particular socket option
     that is being set or retrieved. For more information about the requirements for the 
     <i>Irp</i> parameter for each of the supported socket options, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571186">WSK Socket Options</a>.

If the 
     <i>RequestType</i> parameter is set to 
     <b>WskIoctl</b>, the 
     <i>Irp</i> parameter is required, is optional, or must be <b>NULL</b> depending on the particular I/O control
     operation that is being performed. For more information about the requirements for the 
     <i>Irp</i> parameter for each of the supported I/O control operations, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/wsk-socket-ioctl-operations">WSK Socket IOCTL
     Operations</a>.


## -returns
<b>WskControlSocket</b> returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The control operation completed successfully. If the WSK application specified a pointer to an
       IRP in the 
       <i>Irp</i> parameter, the IRP will be completed with success status, and the number of bytes that is
       returned in the buffer that is pointed to by the 
       <i>OutputBuffer</i> parameter will be returned in the 
       <b>IoStatus.Information</b> field of the IRP.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>The WSK subsystem could not complete the control operation immediately. The WSK subsystem will
       complete the IRP after it has completed the control operation. The status of the control operation
       will be returned in the 
       <b>IoStatus.Status</b> field of the IRP. If the operation succeeds, the number of bytes that is
       returned in the buffer that is pointed to by the 
       <i>OutputBuffer</i> parameter will be returned in the 
       <b>IoStatus.Information</b> field of the IRP.
<dl>
<dt><b>STATUS_EVENT_PENDING</b></dt>
</dl>The WSK subsystem could not complete the control operation immediately. This value is returned
       only when a WSK application is disabling an event callback function on a socket when there are
       currently in-progress calls to that event callback function and when the 
       <i>Irp</i> parameter is <b>NULL</b>. For more information about disabling event callback functions, see 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff570834">SO_WSK_EVENT_CALLBACK</a>.
<dl>
<dt><b>STATUS_FILE_FORCED_CLOSED</b></dt>
</dl>The socket is no longer functional. The IRP will be completed with failure status. The WSK
       application must call the 
       <a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a> function to close the
       socket as soon as possible.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. The IRP will be completed with failure status.

 


## -remarks
If a WSK application specifies 
    <b>WskSetOption</b> or 
    <b>WskGetOption</b> in the 
    <i>RequestType</i> parameter, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571186">WSK Socket Options</a> for more information
    about how the input and output buffers are used for each socket option.

If a WSK application specifies 
    <b>WskIoctl</b> in the 
    <i>RequestType</i> parameter, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/wsk-socket-ioctl-operations">WSK Socket IOCTL Operations</a> for
    more information about how the input and output buffers are used for each I/O control operation.

If the 
    <b>WskControlSocket</b> function returns STATUS_PENDING, any buffers that are pointed to by the 
    <i>InputBuffer</i> parameter or the 
    <i>OutputBuffer</i> parameter must remain valid until the IRP is completed. If the WSK application
    allocated the buffers with one of the 
    <b>ExAllocate<i>Xxx</i></b> functions, it cannot free the memory with the corresponding 
    <b>ExFree<i>Xxx</i></b> function until after the IRP is completed. If the WSK application allocated the buffers on the
    stack, it cannot return from the function that calls the 
    <b>WskControlSocket</b> function until after the IRP is completed.

Callers of the 
    <b>WskControlSocket</b> function must be running at IRQL &lt;= DISPATCH_LEVEL except when the 
    <i>RequestType</i> parameter is set to 
    <b>WskIoctl</b> and the 
    <i>ControlCode</i> parameter is set to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570815">SIO_ADDRESS_LIST_QUERY</a>, 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570814">SIO_ADDRESS_LIST_CHANGE</a>, or <a href="https://msdn.microsoft.com/bf380ddf-8171-4ef4-be47-94c7a6aabf0a">SIO_ADDRESS_LIST_SORT</a>. In this
    situation, callers must be running at IRQL = PASSIVE_LEVEL.


## -see-also
<dl>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk-_wsk_provider_basic_dispatch.md">WSK_PROVIDER_BASIC_DISPATCH</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk-_wsk_provider_connection_dispatch.md">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk-_wsk_provider_datagram_dispatch.md">
   WSK_PROVIDER_DATAGRAM_DISPATCH</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk-_wsk_provider_listen_dispatch.md">WSK_PROVIDER_LISTEN_DISPATCH</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/wsk-socket-ioctl-operations">WSK Socket IOCTL Operations</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571186">WSK Socket Options</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_CONTROL_SOCKET callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

