---
UID: NF:ntifs.FsRtlRegisterUncProvider
title: FsRtlRegisterUncProvider function (ntifs.h)
description: The FsRtlRegisterUncProvider routine registers a network redirector as a universal naming convention (UNC) provider with the system multiple UNC provider (MUP).
old-location: ifsk\fsrtlregisteruncprovider.htm
tech.root: ifsk
ms.assetid: 25bd13de-cbac-408f-b985-e131499f05f0
ms.date: 04/16/2018
keywords: ["FsRtlRegisterUncProvider function"]
ms.keywords: FsRtlRegisterUncProvider, FsRtlRegisterUncProvider routine [Installable File System Drivers], fsrtlref_275d75b9-0033-4cfc-bb22-5ebfcab8d6ba.xml, ifsk.fsrtlregisteruncprovider, ntifs/FsRtlRegisterUncProvider
f1_keywords:
 - "ntifs/FsRtlRegisterUncProvider"
 - "FsRtlRegisterUncProvider"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
- FsRtlRegisterUncProvider
product:
- Windows
targetos: Windows
req.typenames: 
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlRegisterUncProvider function


## -description


The <b>FsRtlRegisterUncProvider</b> routine registers a network redirector as a universal naming convention (UNC) provider with the system multiple UNC provider (MUP).


## -parameters




### -param MupHandle [out]

A pointer to a location in which to return a MUP handle to be used when calling <b>FsRtlRegisterUncProvider</b> to deregister the network redirector. The returned handle is valid only if <b>FsRtlRegisterUncProvider</b> returns STATUS_SUCCESS.


### -param RedirectorDeviceName

<p>A pointer to a Unicode string that contains the device name of the network redirector. </p>


### -param MailslotsSupported [in]

Set to <b>TRUE</b> if the network redirector supports mailslots. This option is normally reserved for use by the Microsoft SMB redirector.


## -returns



<b>FsRtlRegisterUncProvider</b> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value such as one of the following: 

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
The execution mode of the original requester for  the IRP operation sent to MUP was not from kernel mode. 

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
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was passed to MUP in the IRP.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_USER_BUFFER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was passed in the <i>RedirDevName</i> parameter or an abnormal termination occurred. 

</td>
</tr>
</table>
 




## -remarks



A network redirector must register with the MUP to handle UNC names. MUP is a kernel-mode component responsible for channeling all remote file system accesses using a Universal Naming Convention (UNC) name to a network redirector (the UNC provider) that is capable of handling the remote file system requests. MUP is involved when a UNC path is used by an application as illustrated by the following example that could be executed from a command line: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>notepad \\server\public\readme.txt</pre>
</td>
</tr>
</table></span></div>
MUP is not involved during an operation that creates a mapped drive letter (the "NET USE" command, for example). This operation is handled by the multiple provider router (MPR) and a user-mode WNet provider DLL for the network redirector. However, a user-mode WNet provider DLL might communicate directly with a kernel-mode network redirector driver during this operation.

On Windows Server 2003, Windows XP, and Windows 2000, remote file operations performed on a mapped drive that does not represent a Distributed File System (DFS) drive don't go through MUP. These operations go directly to the network provider that handled the drive letter mapping.

For network redirectors that conform to the Windows Vistaredirector model, MUP is involved even when a mapped network drive is used. File operations performed on the mapped drive go through MUP to the network redirector. Note that in this case that MUP simply passes the operation to the network redirector that is involved.

Network redirectors that conform to the Windows Vista redirector model should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex">FsRtlRegisterUncProviderEx</a>, not <b>FsRtlRegisterUncProvider</b>.

<b>FsRtlRegisterUncProvider</b> sends a private file system control (FSCTL) to MUP to perform the registration. 

The ProviderOrder registry value determines the order in which MUP issues prefix resolution requests to individual network redirectors. This registry value is located under the following registry key: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HKLM\CurrentControlSet\Control\NetworkProvider\Order</pre>
</td>
</tr>
</table></span></div>
Changes to the ProviderOrder registry value require a reboot to take effect in MUP on Windows Server 2003, Windows XP, and Windows 2000. 

Only one network provider on a system can support mailslots. So the <i>MailslotsSupported</i> parameter is normally only set to <b>TRUE</b> for the Microsoft SMB redirector.

A driver calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice">IoCreateDevice</a> to create a device object for a network redirector that registers as a UNC provider (a driver that calls <b>FsRtlRegisterUncProvider</b>) must pass FILE_REMOTE_DEVICE as one of the options in the <i>DeviceCharacteristics</i> parameter that is passed to <b>IoCreateDevice</b>.

To deregister a UNC provider, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff545865">FsRtlDeregisterUncProvider</a> and pass the <i>MupHandle</i> parameter.

If a driver registers as a local disk file system (calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice">IoCreateDevice</a> with the <i>DeviceType</i> parameter set to FILE_DEVICE_DISK_FILE_SYSTEM rather than FILE_NETWORK_FILE_SYSTEM, for example), the driver must not call <b>FsRtlRegisterUncProvider</b> to register as a UNC provider with MUP.

For more information, see the following sections in the Design Guide:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/support-for-unc-naming-and-mup">Support for UNC Naming and MUP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mup-changes-in-microsoft-windows-vista">MUP Changes in Microsoft Windows Vista</a>





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545865">FsRtlDeregisterUncProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex">FsRtlRegisterUncProviderEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ni-ntifs-ioctl_redir_query_path_ex">IOCTL_REDIR_QUERY_PATH_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice">IoCreateDevice</a>
 

 

