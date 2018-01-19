---
UID: NI:ntifs.IOCTL_REDIR_QUERY_PATH
title: IOCTL_REDIR_QUERY_PATH
author: windows-driver-content
description: The IOCTL_REDIR_QUERY_PATH control code is sent by the multiple UNC provider (MUP) to network redirectors to determine which provider can handle a specific UNC path in a name-based operation, typically an IRP_MJ_CREATE request.
old-location: ifsk\ioctl_redir_query_path.htm
old-project: ifsk
ms.assetid: 876453a7-922e-4ab7-a609-64d31e60ce88
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlUpperOplockFsctrl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_REDIR_QUERY_PATH
req.alt-loc: ntifs.h
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
req.typenames: TOKEN_TYPE
---

# IOCTL_REDIR_QUERY_PATH IOCTL



## -description
The <b>IOCTL_REDIR_QUERY_PATH</b> control code is sent by the multiple UNC provider (MUP) to network redirectors to determine which provider can handle a specific UNC path in a name-based operation, typically an IRP_MJ_CREATE request. This request is referred to as "prefix resolution."

MUP is a kernel-mode component responsible for channeling all remote file system accesses that use a UNC name to a network redirector (the UNC provider) capable of handling the remote file system requests. MUP is involved when a UNC path is used as illustrated by the following example that could be executed from a command line:



## -syntax

````
notepad \\server\public\readme.txt
````


## -ioctlparameters

### -input-buffer
<b>IrpSp-&gt;Parameters.DeviceIoControl.Type3InputBuffer</b> is set to a <b>QUERY_PATH_REQUEST</b> data structure that contains the request. 

<b>PathNameLength</b>

The length, in bytes, of the Unicode string contained in the <b>FilePathName</b> member.

<b>SecurityContext</b>

A pointer to the security context.

<b>FilePathName</b>

A non-NULL terminated Unicode string of the form \&lt;server&gt;\&lt;share&gt;\&lt;path&gt;. The length of the string, in bytes, is specified by the <b>PathNameLength</b> member.

 


### -input-buffer-length

<text></text>

### -output-buffer
<b>IRP-&gt;UserBuffer</b> is set to a <b>QUERY_PATH_REQUEST</b> data structure that contains the response.

<b>LengthAccepted</b>

The length, in bytes, of the prefix claimed by the provider from the Unicode string path that is specified in the <b>FilePathName</b> member of the <b>QUERY_PATH_REQUEST</b> structure.

 


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Status</b> member is set to STATUS_SUCCESS on success if the \\server\share prefix name is recognized or to an appropriate NTSTATUS value, such as one of the following:  



 The network path cannot be located. The machine name (\\server, for example) is not valid or the network redirector cannot resolve the machine name (using whatever name resolution mechanisms are available). 

The specified share name cannot be found on the remote server. The machine name (\\server, for example) is valid, but specified share name cannot be found on the remote server.

There were insufficient resources available to allocate memory for buffers.

An IOCTL_REDIR_QUERY_PATH request should only come from MUP, and the <b>RequestorMode</b> member of the IRP structure should always be <b>KernelMode</b>. This error code is returned if the <b>RequestorMode</b> of the calling thread was not <b>KernelMode</b>. 

The <b>PathNameLength</b> member in the <b>QUERY_PATH_REQUEST</b> structure exceeds the maximum allowable length, UNICODE_STRING_MAX_BYTES, for a Unicode string. 

If the prefix resolution operation failed due to invalid or incorrect credentials, the provider should return the exact error code that the remote server returns; these error codes must not be translated to STATUS_BAD_NETWORK_NAME or STATUS_BAD_NETWORK_PATH. Error codes like STATUS_LOGON_FAILURE and  STATUS_ACCESS_DENIED serve as a feedback mechanism to the user that indicate the requirement to use appropriate credentials. These error codes are also used in certain cases to prompt the user automatically for credentials. Without these error codes, the user might assume that the machine is not accessible. 

If the network redirector is unable to resolve a prefix, it must return an NTSTATUS code that closely matches the intended semantics from the above list of recommended NTSTATUS codes. A network redirector must not return the actual encountered error (STATUS_CONNECTION_REFUSED, for example) directly to MUP if the NTSTATUS code is not from the above list. 


## -remarks
Network redirectors should only honor kernel-mode senders of this IOCTL, by verifying that the <b>RequestorMode</b> member of the IRP structure is <b>KernelMode</b>. 

Note that IOCTL_REDIR_QUERY_PATH is a METHOD_NEITHER IOCTL. This means that the input and output buffers might not be at the same address. A common mistake by UNC providers is to assume that the input buffer and the output buffer are the same and to use the input buffer pointer to provide the response.

When a UNC provider receives an IOCTL_REDIR_QUERY_PATH request, it has to determine whether it can handle the UNC path specified in the <b>FilePathName</b> member of the <b>QUERY_PATH_REQUEST</b> structure. If so, it has to update the <b>LengthAccepted</b> member of the <b>QUERY_PATH_RESPONSE</b> structure with the length, in bytes, of the prefix it has claimed and complete the IRP with STATUS_SUCCESS. If the provider cannot handle the UNC path specified, it must fail the IOCTL_REDIR_QUERY_PATH request with an appropriate NTSTATUS error code and must not update the <b>LengthAccepted</b> member of the <b>QUERY_PATH_RESPONSE</b> structure. Providers must not modify any of the other members or the <b>FilePathName</b> string under any condition. 

The length of the prefix claimed by the provider depends on an individual UNC provider. Most providers claim the \\&lt;servername&gt;\&lt;sharename &gt; part of a path of the form \\&lt;servername&gt;\&lt;sharename&gt;\&lt;path&gt;. For example, if a provider claimed \\server\public given a path \\server\public\dir1\dir2, all name-based operations for the prefix \\server\public (\server\public\file1, for example) will be routed to that provider automatically without any prefix resolution because the prefix is already in the prefix cache. However, a path with the prefix \server\marketing\presentation will go through prefix resolution.

If a network redirector claims a server name (\\server, for example),all requests for shares on this server will go to this network redirector. This behavior is only acceptable if there is no possibility of another share on the same server being accessed by a different network redirector. For example, a network redirector that claims \\server of a UNC path will prevent access by other network redirectors to other shares on this server (WebDAV access to \\server\web, for example). 

For more information, see the following sections in the Design Guide:


<a href="https://msdn.microsoft.com/07c4a498-10c7-41b2-aaeb-73cab946f392">Support for UNC Naming and MUP</a>



<a href="https://msdn.microsoft.com/8ca2f9bc-14f1-45d3-a397-f3e5459cf8ec">MUP Changes in Microsoft Windows Vista</a>



## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlderegisteruncprovider.md">FsRtlDeregisterUncProvider</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex~r3.md">FsRtlRegisterUncProviderEx</a>
</dt>
<dt>
<a href="..\ntifs\ni-ntifs-ioctl_redir_query_path_ex.md">IOCTL_REDIR_QUERY_PATH_EX</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IOCTL_REDIR_QUERY_PATH control code%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

