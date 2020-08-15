---
UID: NC:wsk.PFN_WSK_GET_NAME_INFO
title: PFN_WSK_GET_NAME_INFO (wsk.h)
description: The WskGetNameInfo function provides protocol-independent translation from a transport address to a host name.
old-location: netvista\wskgetnameinfo.htm
tech.root: netvista
ms.assetid: 99e10a70-90a7-4d96-ae5f-ba82d8c4c1a8
ms.date: 05/02/2018
keywords: ["PFN_WSK_GET_NAME_INFO callback function"]
ms.keywords: PFN_WSK_GET_NAME_INFO, PFN_WSK_GET_NAME_INFO callback, WskGetNameInfo, WskGetNameInfo callback function [Network Drivers Starting with Windows Vista], netvista.wskgetnameinfo, wsk/WskGetNameInfo, wskref_cebad0ad-55bc-4fae-9c73-5a501417ea5c.xml
f1_keywords:
 - "wsk/WskGetNameInfo"
 - "WskGetNameInfo"
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
- wsk.h
api_name:
- WskGetNameInfo
targetos: Windows
req.typenames: 
---

# PFN_WSK_GET_NAME_INFO callback function


## -description


The 
  <b>WskGetNameInfo</b> function provides protocol-independent translation from a transport address to a host
  name.


## -parameters




### -param Client 
[in]
[in] A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wsk-client">WSK_CLIENT</a> structure that was returned through
     the 
     <i>WskProviderNpi</i> parameter of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskcaptureprovidernpi">
     WskCaptureProviderNPI</a> function.


### -param SockAddr 
[in]
[in] A pointer to a 
     <a href="https://docs.microsoft.com/windows/desktop/api/ws2def/ns-ws2def-sockaddr">SOCKADDR</a> structure that contains the IP address
     and port number of the socket.


### -param SockAddrLength 
[in]
[in] Specifies the length, in bytes, of the buffer pointed to by the 
     <i>SockAddr</i> parameter. The value of 
     <i>SockAddrLength</i> should not exceed the size of the 
     <a href="https://docs.microsoft.com/windows/win32/api/ws2def/ns-ws2def-sockaddr_storage_lh">SOCKADDR_STORAGE</a> structure.


### -param NodeName 
[out, optional]
[out] An optional pointer to a 
     <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains a
     Unicode string that represents a host (node) name. On success, the Unicode host name is written as a
     Fully Qualified Domain Name (FQDN) by default. The caller must provide a UNICODE_STRING buffer large
     enough to hold the Unicode host name, which includes the terminating NULL character. If the 
     <i>NodeBuffer</i> parameter is <b>NULL</b>, the caller does not want to receive a host name string. 
     <i>NodeBuffer</i> and 
     <i>ServiceBuffer</i> must not both be <b>NULL</b>.


### -param ServiceName 
[out, optional]
[out] An optional pointer to a 
     <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains a
     Unicode string that represents a service name associated with the port number. The caller must provide a
     UNICODE_STRING buffer large enough to hold the Unicode service name, which includes the terminating NULL
     character. If the 
     <i>NodeBuffer</i> parameter is <b>NULL</b>, the caller does not want to receive a service name string. 
     <i>NodeBuffer</i> and 
     <i>ServiceBuffer</i> must not both be <b>NULL</b>.


### -param Flags 
[in]
[in] A ULONG value that is used to customize the processing of this function.
     

The following flags are available:





#### NI_DGRAM

Indicates that the service is a datagram service. This flag is necessary for the few services
       that provide different port numbers for UDP and TCP service.



#### NI_NAMEREQD

Indicates that a host name that cannot be resolved by DNS results in an error.



#### NI_NOFQDN

Results in a local host having only its Relative Distinguished Name (RDN) returned in the 
       <i>NodeName</i> parameter.



#### NI_NUMERICHOST

Indicates that the function returns the numeric form of the host name instead of its name, a
       reverse DNS lookup. The numeric form of the host name is also returned if the host name cannot be
       resolved by DNS.



#### NI_NUMERICSERV

Indicates that the function returns the port number of the service instead of its name. Also, if
       a host name is not found for an IP address (127.0.0.2, for example), the host name is returned as the
       IP address.


### -param OwningProcess 
[in, optional]
[in] An optional pointer to the process from which the function retrieves the security context.
     This security context indicates the user account context in which the function processes the name
     resolution request.
     

If this parameter is <b>NULL</b>, the function processes the name resolution request in the context of a
     predefined local account with minimal privileges.

If this parameter is not <b>NULL</b> and an impersonation token is in effect for the calling thread, this
     function fails and returns STATUS_INVALID_PARAMETER.


### -param OwningThread 
[in, optional]
[in] An optional pointer to the thread from which the function retrieves the security context.
     This parameter can be non-<b>NULL</b> only if 
     <i>OwningProcess</i> is non-<b>NULL</b>. Otherwise, this function fails and returns STATUS_INVALID_PARAMETER.
     

If this parameter is not <b>NULL</b> and an impersonation token is in effect for the calling thread, this
     function fails and returns STATUS_INVALID_PARAMETER.


### -param Irp 
[in, out]
[in/out] A pointer to an I/O request packet (IRP) to use to complete the request asynchronously.
     Upon completion of the request, 
     <i>Irp</i> ->
     <b>Iostatus.Information</b> will hold the returned status code.


## -returns



<b>WskGetNameInfo</b> returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MATCH</b></dt>
</dl>
</td>
<td width="60%">
The host name cannot be resolved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The function completed successfully. If the WSK application specified a pointer to an IRP in the
       
       <i>Irp</i> parameter, the IRP will be completed with a success status.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not complete the function immediately. The WSK subsystem will complete
       the IRP after it has completed the control operation. The status of the control operation will be
       returned in the 
       <b>IoStatus.Status</b> field of the IRP.

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



The process to which the 
    <i>OwningProcess</i> parameter points, or the thread to which the 
    <i>OwningThread</i> process points, indicates the security context for this function. The user account
    that is indicated by the security context indicates the context for the function's name resolution
    request.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ws2def/ns-ws2def-sockaddr">SOCKADDR</a>



<a href="https://docs.microsoft.com/windows/win32/api/ws2def/ns-ws2def-sockaddr_storage_lh">SOCKADDR_STORAGE</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wsk-client">WSK_CLIENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskcaptureprovidernpi">WskCaptureProviderNPI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_get_address_info">WskGetAddressInfo</a>
 

 

