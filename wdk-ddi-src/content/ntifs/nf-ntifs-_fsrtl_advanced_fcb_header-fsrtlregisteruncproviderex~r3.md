---
UID: NF:ntifs.FsRtlRegisterUncProviderEx~r3
title: FsRtlRegisterUncProviderEx function (ntifs.h)
description: The FsRtlRegisterUncProviderEx routine registers a network redirector as a universal naming convention (UNC) provider with the system multiple UNC provider (MUP).
old-location: ifsk\fsrtlregisteruncproviderex.htm
tech.root: ifsk
ms.assetid: 5b7302c1-2f31-4b9f-bddb-7b35bbee4a2c
ms.date: 03/29/2018
keywords: ["FsRtlRegisterUncProviderEx function"]
ms.keywords: FsRtlRegisterUncProviderEx, FsRtlRegisterUncProviderEx routine [Installable File System Drivers], fsrtlref_ae033ff2-3d3a-468c-973d-d6a78a2293a2.xml, ifsk.fsrtlregisteruncproviderex, ntifs/FsRtlRegisterUncProviderEx
f1_keywords:
 - "ntifs/FsRtlRegisterUncProviderEx"
 - "FsRtlRegisterUncProviderEx"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Windows Vista and later versions.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlRegisterUncProviderEx
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlRegisterUncProviderEx function


## -description


The <b>FsRtlRegisterUncProviderEx</b> routine registers a network redirector as a universal naming convention (UNC) provider with the system multiple UNC provider (MUP).


## -parameters




### -param MupHandle 
[out]
A pointer to a location in which to return a MUP handle to be used when calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545865">FsRtlDeregisterUncProvider</a> to deregister the network redirector. The returned handle is valid only if <b>FsRtlRegisterUncProviderEx</b> returns STATUS_SUCCESS.


### -param RedirDevName 
[in]
A pointer to a Unicode string that contains the device name of the network redirector. MUP uses this device name to create a symbolic link in the Object Manager namespace whose target is \Device\Mup.


### -param DeviceObject 
[in]
A pointer to an unnamed device object that represents the network redirector.


### -param Flags 
[in]
A bitmask that indicates features supported by the network redirector. A network redirector sets a bit to indicate that a feature is supported. The <i>Flags</i> parameter has two options:

FSRTL_UNC_PROVIDER_FLAGS_MAILSLOTS_SUPPORTED

The network redirector supports mailslots. This option is normally reserved for use by the Microsoft SMB redirector.

FSRTL_UNC_PROVIDER_FLAGS_CSC_ENABLED

The network redirector supports offline access using client-side caching.


## -returns



<b>FsRtlRegisterUncProviderEx</b> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The requester mode of the IRP that is sent to MUP was not from kernel mode.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl>
</td>
<td width="60%">
An access violation occurred when attempting access to the MUP device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DATATYPE_MISALIGNMENT</b></dt>
</dl>
</td>
<td width="60%">
There was a misalignment of data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There were insufficient resources available to allocate memory for buffers.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
A request was made to register a known provider that was already registered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>RedirDevName</i> parameter was invalid because the length of <i>RedirDevName</i> was zero.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
An object type mismatch was encountered with the <i>DeviceObject</i> parameter.

</td>
</tr>
</table>
 




## -remarks



A network redirector must register with the multiple UNC provider (MUP) to handle Universal Naming Convention (UNC) names. MUP is a kernel-mode component responsible for channeling all remote file system accesses using a Universal Naming Convention (UNC) name to a network redirector (the UNC provider) that is capable of handling the remote file system requests. MUP is involved when a UNC path is used by an application as illustrated by the following example that could be executed from a command line:


```
notepad \\server\public\readme.txt
```

MUP is not involved during an operation that creates a mapped drive letter (the "NET USE" command, for example). This operation is handled by the multiple provider router (MPR) and a user-mode WNet provider DLL for the network redirector. However, a user-mode WNet provider DLL might communicate directly with a kernel-mode network redirector driver during this operation.

For network redirectors that conform to the Windows Vista redirector model, MUP is involved even when a mapped network drive is used. File operations performed on the mapped drive go through MUP to the network redirector. Note that in this case, MUP simply passes the operation to the network redirector that is involved.

<b>FsRtlRegisterUncProviderEx</b> sends a private file system control (FSCTL) to MUP to perform the registration.

The device name specified in the <i>RedirDevName</i> parameter in the call to <b>FsRtlRegisterUncProviderEx</b> becomes a symbolic link to \device\Mup in the object manager namespace. Also, an open request of the device name, <i>RedirDevName</i>, will route itself to the actual network redirector device object pointed to by the <i>DeviceObject</i> parameter.

Network redirectors that call <b>FsRtlRegisterUncProviderEx</b> must not register themselves as a file system (network redirectors must not call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfilesystem">IoRegisterFileSystem</a>). Network mini-redirectors that use the Windows Vista RDBSS (dynamic or static linking) will not be registered as a file system.

File objects on the remote file system stack owned by a network redirector that conforms to the Windows Vista redirector model resolve to MUP. So <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogetdeviceattachmentbaseref">IoGetDeviceAttachmentBaseRef</a> returns the device object for MUP, not the network redirector that owns the file object. However, the content of the file object is still owned by the network redirector.

The ProviderOrder registry value determines the order in which MUP issues prefix resolution requests to individual network redirectors. This order can be changed dynamically without a reboot. This registry value is located under the following registry key:


```
HKLM\CurrentControlSet\Control\NetworkProvider\Order
```

Only one network provider on a system can support mailslots. So the FSRTL_UNC_PROVIDER_FLAGS_MAILSLOTS_SUPPORTED option in the <i>Flags</i> parameter is normally only set for the Microsoft SMB redirector.

To deregister a UNC provider, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff545865">FsRtlDeregisterUncProvider</a> and pass the <i>MupHandle</i> parameter.

If a driver registers as a local disk file system (by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice">IoCreateDevice</a> with the <i>DeviceType</i> parameter set to FILE_DEVICE_DISK_FILE_SYSTEM), the driver must not call <b>FsRtlRegisterUncProviderEx</b> to register as a UNC provider with MUP.

For more information, see the following sections in the Design Guide:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/support-for-unc-naming-and-mup">Support for UNC Naming and MUP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mup-changes-in-microsoft-windows-vista">MUP Changes in Microsoft Windows Vista</a>





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545738">FsRtlCancellableWaitForSingleObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545865">FsRtlDeregisterUncProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncprovider">FsRtlRegisterUncProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ni-ntifs-ioctl_redir_query_path_ex">IOCTL_REDIR_QUERY_PATH_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice">IoCreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogetdeviceattachmentbaseref">IoGetDeviceAttachmentBaseRef</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfilesystem">IoRegisterFileSystem</a>
 

 

