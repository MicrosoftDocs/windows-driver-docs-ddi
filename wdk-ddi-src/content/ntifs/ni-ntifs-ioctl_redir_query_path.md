---
UID: NI:ntifs.IOCTL_REDIR_QUERY_PATH
title: IOCTL_REDIR_QUERY_PATH (ntifs.h)
description: The IOCTL_REDIR_QUERY_PATH control code is sent by the multiple UNC provider (MUP) to network redirectors to determine which provider can handle a specific UNC path in a name-based operation, typically an IRP_MJ_CREATE request.
old-location: ifsk\ioctl_redir_query_path.htm
tech.root: ifsk
ms.assetid: 876453a7-922e-4ab7-a609-64d31e60ce88
ms.date: 04/16/2018
ms.keywords: IOCTL_REDIR_QUERY_PATH, IOCTL_REDIR_QUERY_PATH control, IOCTL_REDIR_QUERY_PATH control code [Installable File System Drivers], ifsk.ioctl_redir_query_path, ioctl_ref_f46fa4a1-0546-4d70-8490-7a233a2e743f.xml, ntifs/IOCTL_REDIR_QUERY_PATH
f1_keywords:
 - "ntifs/IOCTL_REDIR_QUERY_PATH"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- IOCTL_REDIR_QUERY_PATH
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_REDIR_QUERY_PATH IOCTL


## -description


The <b>IOCTL_REDIR_QUERY_PATH</b> control code is sent by the multiple UNC provider (MUP) to network redirectors to determine which provider can handle a specific UNC path in a name-based operation, typically an IRP_MJ_CREATE request. This request is referred to as "prefix resolution."

MUP is a kernel-mode component responsible for channeling all remote file system accesses that use a UNC name to a network redirector (the UNC provider) capable of handling the remote file system requests. MUP is involved when a UNC path is used as illustrated by the following example that could be executed from a command line:
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

On Windows Server 2003, Windows XP, and Windows 2000, remote file operations that are performed on a mapped drive that does not represent a Distributed File System (DFS) drive don't go through MUP. These operations go directly to the network provider that handled the drive letter mapping.

For network redirectors that conform to the Windows Vista redirector model, MUP is involved even when a mapped network drive is used. File operations performed on the mapped drive go through MUP to the network redirector. Note that in this case, MUP simply passes the operation to the network redirector that is involved.

The IOCTL_REDIR_QUERY_PATH control code is sent to network redirectors that have registered with MUP as Universal Naming Convention (UNC) providers by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlregisteruncprovider">FsRtlRegisterUncProvider</a>. There can be multiple UNC providers registered with MUP. 

The prefix resolution operation serves two purposes:
<ul>
<li>
The name-based operation that resulted in the prefix resolution is routed to the provider that claims the prefix. If successful, MUP ensures that subsequent handle-based operations (IRP_MJ_READ and IRP_MJ_WRITE, for example) go to the same provider completely bypassing MUP.

</li>
<li>
The provider and the prefix that it claimed are entered in a prefix cache that is maintained by MUP. For subsequent name-based operations, MUP uses this prefix cache to determine whether a provider has already claimed a prefix before MUP attempts to perform a prefix resolution. Each entry in this prefix cache is subject to a timeout (referred to as TTL) once it is added to the cache. An entry is thrown away after this timeout expires, at which point of time, MUP will perform prefix resolution again for this prefix on a subsequent name-based operation.

</li>
</ul>

## -ioctlparameters




### -input-buffer

<b>IrpSp->Parameters.DeviceIoControl.Type3InputBuffer</b> is set to a <b>QUERY_PATH_REQUEST</b> data structure that contains the request. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _QUERY_PATH_REQUEST {
  ULONG  PathNameLength;
  PIO_SECURITY_CONTEXT SecurityContext;
  WCHAR  FilePathName[1];
} QUERY_PATH_REQUEST, *PQUERY_PATH_REQUEST;</pre>
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
<b>PathNameLength</b>

</td>
<td>
The length, in bytes, of the Unicode string contained in the <b>FilePathName</b> member.

</td>
</tr>
<tr>
<td>
<b>SecurityContext</b>

</td>
<td>
A pointer to the security context.

</td>
</tr>
<tr>
<td>
<b>FilePathName</b>

</td>
<td>
A non-NULL terminated Unicode string of the form \<server>\<share>\<path>. The length of the string, in bytes, is specified by the <b>PathNameLength</b> member.

</td>
</tr>
</table>
 


### -input-buffer-length








### -output-buffer

<b>IRP->UserBuffer</b> is set to a <b>QUERY_PATH_REQUEST</b> data structure that contains the response.

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
The length, in bytes, of the prefix claimed by the provider from the Unicode string path that is specified in the <b>FilePathName</b> member of the <b>QUERY_PATH_REQUEST</b> structure.

</td>
</tr>
</table>
 


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Status</b> member is set to STATUS_SUCCESS on success if the \\server\share prefix name is recognized or to an appropriate NTSTATUS value, such as one of the following:  



If the network redirector is unable to resolve a prefix, it must return an NTSTATUS code that closely matches the intended semantics from the above list of recommended NTSTATUS codes. A network redirector must not return the actual encountered error (STATUS_CONNECTION_REFUSED, for example) directly to MUP if the NTSTATUS code is not from the above list. 


#### -STATUS_BAD_NETWORK_NAME

The specified share name cannot be found on the remote server. The machine name (\\server, for example) is valid, but specified share name cannot be found on the remote server.


#### -STATUS_BAD_NETWORK_PATH

 The network path cannot be located. The machine name (\\server, for example) is not valid or the network redirector cannot resolve the machine name (using whatever name resolution mechanisms are available). 


#### -STATUS_INSUFFICIENT_RESOURCES

There were insufficient resources available to allocate memory for buffers.


#### -STATUS_INVALID_DEVICE_REQUEST

An IOCTL_REDIR_QUERY_PATH request should only come from MUP, and the <b>RequestorMode</b> member of the IRP structure should always be <b>KernelMode</b>. This error code is returned if the <b>RequestorMode</b> of the calling thread was not <b>KernelMode</b>. 


#### -STATUS_INVALID_PARAMETER

The <b>PathNameLength</b> member in the <b>QUERY_PATH_REQUEST</b> structure exceeds the maximum allowable length, UNICODE_STRING_MAX_BYTES, for a Unicode string. 


#### -STATUS_LOGON_FAILURE or STATUS_ACCESS_DENIED

If the prefix resolution operation failed due to invalid or incorrect credentials, the provider should return the exact error code that the remote server returns; these error codes must not be translated to STATUS_BAD_NETWORK_NAME or STATUS_BAD_NETWORK_PATH. Error codes like STATUS_LOGON_FAILURE and  STATUS_ACCESS_DENIED serve as a feedback mechanism to the user that indicate the requirement to use appropriate credentials. These error codes are also used in certain cases to prompt the user automatically for credentials. Without these error codes, the user might assume that the machine is not accessible. 


## -remarks



Network redirectors should only honor kernel-mode senders of this IOCTL, by verifying that the <b>RequestorMode</b> member of the IRP structure is <b>KernelMode</b>. 

Note that IOCTL_REDIR_QUERY_PATH is a METHOD_NEITHER IOCTL. This means that the input and output buffers might not be at the same address. A common mistake by UNC providers is to assume that the input buffer and the output buffer are the same and to use the input buffer pointer to provide the response.

When a UNC provider receives an IOCTL_REDIR_QUERY_PATH request, it has to determine whether it can handle the UNC path specified in the <b>FilePathName</b> member of the <b>QUERY_PATH_REQUEST</b> structure. If so, it has to update the <b>LengthAccepted</b> member of the <b>QUERY_PATH_RESPONSE</b> structure with the length, in bytes, of the prefix it has claimed and complete the IRP with STATUS_SUCCESS. If the provider cannot handle the UNC path specified, it must fail the IOCTL_REDIR_QUERY_PATH request with an appropriate NTSTATUS error code and must not update the <b>LengthAccepted</b> member of the <b>QUERY_PATH_RESPONSE</b> structure. Providers must not modify any of the other members or the <b>FilePathName</b> string under any condition. 

The length of the prefix claimed by the provider depends on an individual UNC provider. Most providers claim the \\<servername>\<sharename > part of a path of the form \\<servername>\<sharename>\<path>. For example, if a provider claimed \\server\public given a path \\server\public\dir1\dir2, all name-based operations for the prefix \\server\public (\server\public\file1, for example) will be routed to that provider automatically without any prefix resolution because the prefix is already in the prefix cache. However, a path with the prefix \server\marketing\presentation will go through prefix resolution.

If a network redirector claims a server name (\\server, for example),all requests for shares on this server will go to this network redirector. This behavior is only acceptable if there is no possibility of another share on the same server being accessed by a different network redirector. For example, a network redirector that claims \\server of a UNC path will prevent access by other network redirectors to other shares on this server (WebDAV access to \\server\web, for example). 

For more information, see the following sections in the Design Guide:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/support-for-unc-naming-and-mup">Support for UNC Naming and MUP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mup-changes-in-microsoft-windows-vista">MUP Changes in Microsoft Windows Vista</a>





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545865">FsRtlDeregisterUncProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlregisteruncproviderex">FsRtlRegisterUncProviderEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ni-ntifs-ioctl_redir_query_path_ex">IOCTL_REDIR_QUERY_PATH_EX</a>
 

 

