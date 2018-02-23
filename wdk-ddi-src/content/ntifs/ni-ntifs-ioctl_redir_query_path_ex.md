---
UID: NI:ntifs.IOCTL_REDIR_QUERY_PATH_EX
title: IOCTL_REDIR_QUERY_PATH_EX
author: windows-driver-content
description: The IOCTL_REDIR_QUERY_PATH_EX control code is sent by the multiple UNC provider (MUP) on Windows Vista or later to network redirectors to determine which provider can handle a specific UNC path in a name-based operation, typically an IRP_MJ_CREATE request.
old-location: ifsk\ioctl_redir_query_path_ex.htm
old-project: ifsk
ms.assetid: 290825dd-d5f6-4e9b-b1a3-3e146d3e1856
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.ioctl_redir_query_path_ex, IOCTL_REDIR_QUERY_PATH_EX control code [Installable File System Drivers], IOCTL_REDIR_QUERY_PATH_EX, ntifs/IOCTL_REDIR_QUERY_PATH_EX, ioctl_ref_de59d691-17c8-4e21-8acc-61d2f27c2799.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This IOCTL is available on Windows Vista and later versions.
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	IOCTL_REDIR_QUERY_PATH_EX
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IOCTL_REDIR_QUERY_PATH_EX IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_REDIR_QUERY_PATH_EX</b> control code is sent by the multiple UNC provider (MUP) on Windows Vista or later to network redirectors to determine which provider can handle a specific UNC path in a name-based operation, typically an IRP_MJ_CREATE request. This request is referred to as "prefix resolution." 

MUP is a kernel-mode component responsible for channeling all remote file system accesses using a UNC name to a network redirector (the UNC provider) that is capable of handling the remote file system requests. MUP is involved when a UNC path is used as illustrated by the following example that could be executed from a command line:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>notepad \\server\public\readme.txt</pre>
</td>
</tr>
</table></span></div>MUP is not involved during an operation that creates a mapped drive letter (the "NET USE" command, for example). This operation is handled by the multiple provider router (MPR) and a user-mode WNet provider DLL for the network redirector. However, a user-mode WNet provider DLL might communicate directly with a kernel-mode network redirector driver during this operation.

For network redirectors that conform to the Windows Vista redirector model, MUP is involved even when a mapped network drive is used. File operations performed on the mapped drive go through MUP to the network redirector. Note that in this case, MUP simply passes the operation to the network redirector that is involved.

The IOCTL_REDIR_QUERY_PATH_EX control code is sent to network redirectors that have registered with MUP as Universal Naming Convention (UNC) providers by calling <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex~r3.md">FsRtlRegisterUncProviderEx</a>. There can be multiple UNC providers registered with MUP. 

The prefix resolution operation serves two consequences:
<ul>
<li>
The name-based operation that resulted in the prefix resolution is routed to the provider that claims the prefix. If successful, MUP ensures that subsequent handle-based operations (IRP_MJ_READ and IRP_MJ_WRITE, for example) go through MUP to the same provider. Note that this behavior is different for network redirectors that are not in conformance with the Windows Vista redirector model, which will be sent IOCTL_REDIR_QUERY_PATH for prefix resolution. For network redirectors that don't conform with the Windows Vista redirector model, MUP is completely bypassed for subsequent handle-based operations. 

</li>
<li>
The provider and the prefix that it claimed are entered in a prefix cache maintained by MUP. For subsequent name-based operations, MUP uses this prefix cache to determine whether a provider has already claimed a prefix before MUP attempts to perform a prefix resolution. Each entry in this prefix cache is subject to a timeout (referred to as TTL) once it is added to the cache. An entry is thrown away after this timeout expires, at which point MUP will perform prefix resolution again for this prefix on a subsequent name-based operation.

</li>
</ul>

## -ioctlparameters




### -input-buffer

<b>IrpSp-&gt;Parameters.DeviceIoControl.Type3InputBuffer</b> is set to a <b>QUERY_PATH_REQUEST_EX</b> data structure that contains the request. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _QUERY_PATH_REQUEST_EX {
  PIO_SECURITY_CONTEXT  pSecurityContext;
  ULONG  EaLength;
  PVOID  pEaBuffer;
  UNICODE_STRING  PathName;
} QUERY_PATH_REQUEST_EX, *PQUERY_PATH_REQUEST_EX;</pre>
</td>
</tr>
</table></span></div>
<table>
<tr>
<th>Structure member</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>pSecurityContext</b>

</td>
<td>
A pointer to the Security context.

</td>
</tr>
<tr>
<td>
<b>EaLength</b>

</td>
<td>
The length, in bytes, of the extended attributes buffer.

</td>
</tr>
<tr>
<td>
<b>pEaBuffer</b>

</td>
<td>
A pointer to the extended attributes buffer.

</td>
</tr>
<tr>
<td>
<b>PathName</b>

</td>
<td>
A non-NULL terminated Unicode string of the form \&lt;server&gt;\&lt;share&gt;\&lt;path&gt;. 

</td>
</tr>
</table>
 


### -input-buffer-length



<text></text>




### -output-buffer

<b>IRP-&gt;UserBuffer</b> is set to a <b>QUERY_PATH_RESPONSE</b> data structure that contains the response.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _QUERY_PATH_RESPONSE {
  ULONG  LengthAccepted;
} QUERY_PATH_RESPONSE, *PQUERY_PATH_RESPONSE;</pre>
</td>
</tr>
</table></span></div>
<table>
<tr>
<th>Structure member</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>LengthAccepted</b>

</td>
<td>
The length, in bytes, of the prefix claimed by the provider from the Unicode string path that is specified in the <b>PathName</b> member of the <b>QUERY_PATH_REQUEST_EX</b> structure.

</td>
</tr>
</table>
 


### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Status</b> member is set to STATUS_SUCCESS on success if the \\server\share prefix name is recognized, or to an appropriate NTSTATUS value, such as one of the following:  



If the network redirector is unable to resolve a prefix, it must return an NTSTATUS code that closely matches the intended semantics from the above list of recommended NTSTATUS codes. A network redirector must not return the actual encountered error (STATUS_CONNECTION_REFUSED, for example) directly to MUP if the NTSTATUS code is not from the above list. 


#### -STATUS_BAD_NETWORK_PATH

The network path cannot be located. The machine name (\\server, for example) is not valid or the network redirector cannot resolve the machine name (using whatever name resolution mechanisms are available). 


#### -STATUS_BAD_NETWORK_NAME

The specified share name cannot be found on the remote server. The machine name (\\server, for example) is valid, but the specified share name cannot be found on the remote server.


#### -STATUS_INSUFFICIENT_RESOURCES

There were insufficient resources available to allocate memory for buffers.


#### -STATUS_INVALID_DEVICE_REQUEST

An IOCTL_REDIR_QUERY_PATH_EX request should only come from MUP and the <b>RequestorMode</b> member of the IRP structure should always be <b>KernelMode</b>. This error code is returned if the requester mode of the calling thread was not <b>KernelMode</b>. 


#### -STATUS_LOGON_FAILURE or STATUS_ACCESS_DENIED

If the prefix resolution operation failed due to invalid or incorrect credentials, the provider should return the exact error code returned by the remote server; these error codes must not be translated to STATUS_BAD_NETWORK_NAME or STATUS_BAD_NETWORK_PATH. Error codes like STATUS_LOGON_FAILURE and STATUS_ACCESS_DENIED serve as a feedback mechanism to the user and indicate the requirement to use appropriate credentials. These error codes are also used in certain cases to prompt the user automatically for credentials. Without these error codes, the user might assume that the machine is not accessible. 


## -remarks



Network redirectors should only honor kernel-mode senders of this IOCTL, by verifying that <b>Irp-&gt;RequestorMode</b> is <b>KernelMode</b>. 

Note that IOCTL_REDIR_QUERY_PATH_EX is a METHOD_NEITHER IOCTL. This means that the input and output buffers might not be at the same address. A common mistake by UNC providers is to assume that the input buffer and the output buffer are the same and use the input buffer pointer to provide the response.

When a UNC provider receives an IOCTL_REDIR_QUERY_PATH_EX request, it has to determine whether it can handle the UNC path that is specified in the <b>PathName</b> member of the <b>QUERY_PATH_REQUEST_EX</b> structure. If so, the UNC provider has to update the <b>LengthAccepted</b> member of the <b>QUERY_PATH_RESPONSE</b> structure with the length, in bytes, of the prefix it has claimed and complete the IRP with STATUS_SUCCESS. If the provider cannot handle the UNC path specified, it must fail the IOCTL_REDIR_QUERY_PATH_EX request with an appropriate NTSTATUS error code and must not update the <b>LengthAccepted</b> member of the <b>QUERY_PATH_RESPONSE</b> structure. Providers must not modify any other members or the <b>PathName</b> member under any condition. 

The length of the prefix claimed by the provider depends on an individual UNC provider. Most providers usually claim the \\&lt;servername&gt;\&lt;sharename &gt; part of a path of the form \\&lt;servername&gt;\&lt;sharename&gt;\&lt;path&gt;. For example, if a provider claimed \\server\public given a path \\server\public\dir1\dir2, all name-based operations for the prefix \\server\public (\server\public\file1, for example) will be routed to that provider automatically without any prefix resolution because the prefix is already in the prefix cache. However, a path with the prefix \server\marketing\presentation will go through prefix resolution.

If a network redirector claims a server name (\\server, for example), all requests for shares on this server will go to this network redirector. This behavior is only acceptable if there is no possibility of another share on the same server being accessed by a different network redirector. For example, a network redirector that claims \\server of a UNC path will prevent access by other network redirectors to other shares on this server (WebDAV access to \\server\web, for example). 

For more information, see the following sections in the Design Guide:


<a href="https://msdn.microsoft.com/07c4a498-10c7-41b2-aaeb-73cab946f392">Support for UNC Naming and MUP</a>



<a href="https://msdn.microsoft.com/8ca2f9bc-14f1-45d3-a397-f3e5459cf8ec">MUP Changes in Microsoft Windows Vista</a>





## -see-also

<a href="..\ntifs\nf-ntifs-fsrtlderegisteruncprovider.md">FsRtlDeregisterUncProvider</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncprovider~r2.md">FsRtlRegisterUncProvider</a>



<a href="..\ntifs\ni-ntifs-ioctl_redir_query_path.md">IOCTL_REDIR_QUERY_PATH</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex~r3.md">FsRtlRegisterUncProviderEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IOCTL_REDIR_QUERY_PATH_EX control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

