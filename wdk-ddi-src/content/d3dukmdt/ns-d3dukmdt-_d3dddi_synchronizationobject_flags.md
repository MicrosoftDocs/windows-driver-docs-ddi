---
UID: NS:d3dukmdt._D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS
title: _D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS (d3dukmdt.h)
description: Identifies attributes of a synchronization object.
old-location: display\d3dddi_synchronizationobject_flags.htm
tech.root: display
ms.assetid: 57e5ea18-ccdd-40a7-9ff5-4d6b94908e7c
ms.date: 05/10/2018
ms.keywords: D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS, D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS structure [Display Devices], D3D_other_Structs_3d266c5b-53c9-47d1-abe9-f492d05660a4.xml, _D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS, d3dukmdt/D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS, display.d3dddi_synchronizationobject_flags
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS is supported beginning with the Windows 7 operating system.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dukmdt.h
api_name:
-	D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS
---

# _D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS structure


## -description


Identifies attributes of a synchronization object.


## -struct-fields




### -field Shared

A UINT value that specifies whether the synchronization object is shared.

If <b>Shared</b> is set to 1 (<b>TRUE</b>), the synchronization object is shared. If <b>Shared</b> is set to zero (<b>FALSE</b>), the synchronization object is not shared.

For more information, see the Remarks section.


### -field NtSecuritySharing

A UINT value that specifies whether the synchronization object is shared with an NT handle, meaning that it  does not have a global <b>D3DKMT_HANDLE</b> kernel-mode handle to the resource.

If <b>NtSecuritySharing</b> is set to 1 (<b>TRUE</b>), the synchronization object is shared but does not have a global <b>D3DKMT_HANDLE</b> handle to the resource.

<div class="alert"><b>Note</b>  If <b>NtSecuritySharing</b> is set to 1,  <b>Shared</b>  must be set to 1.</div>
<div> </div>
For more information, see the Remarks section.

Supported starting with Windows 8.


### -field CrossAdapter

A UINT value that specifies whether the synchronization object is a shared cross-adapter object on a <a href="https://msdn.microsoft.com/ECBB0AA7-50C2-41C8-9DC6-6EEFC5CEEB15">hybrid system</a>.

If <b>CrossAdapter</b> is set to 1 (<b>TRUE</b>), the synchronization object is a shared cross-adapter object. If <b>CrossAdapter</b> is set to zero (<b>FALSE</b>), the synchronization object is not a shared cross-adapter object.

For more information, see <a href="https://msdn.microsoft.com/ECBB0AA7-50C2-41C8-9DC6-6EEFC5CEEB15">Using cross-adapter resources in a hybrid system</a>.


### -field TopOfPipeline

|Value|Meaning|
|--- |--- |
|TRUE|Specifies whether the synchronization object is signaled as soon as the contents of command buffer preceding it is entirely copied to the GPU pipeline, but not necessarily completed execution. This behavior allows reusing command buffers as soon as possible.|
|FALSE|The synchronization object is signaled after the preceding command buffers completed execution.|
 

This value can only be set to 1 (<b>TRUE</b>) for monitored fence synchronization objects, and it should be set to zero (<b>FALSE</b>) for all other synchronization object types.

Supported starting with Windows 10.


### -field NoSignal

|Value|Meaning|
|--- |--- |
|TRUE|Specifies the device this sync object is created or opened on can only submit wait commands for it. An attempt to submit a signal operation when this flag is set will return STATUS_ACCESS_DENIED.|
|FALSE|The synchronization object can be signaled.|
 

This value can only be set to 1 (<b>TRUE</b>) for monitored fence synchronization objects, and it should be set to zero (<b>FALSE</b>) for all other synchronization object types.

Supported starting with Windows 10.


### -field NoWait

|Value|Meaning|
|--- |--- |
|TRUE|Specifies the device this sync object is created or opened on can only submit signal commands for it. An attempt to submit a wait operation when this flag is set will return STATUS_ACCESS_DENIED.|
|FALSE|The synchronization object can be waited on.|
 

This value can only be set to 1 (<b>TRUE</b>) for monitored fence synchronization objects, and it should be set to zero (<b>FALSE</b>) for all other synchronization object types.


This flag cannot be set simultaneously with <b>NoSignal</b> flag.


Supported starting with Windows 10.


### -field NoSignalMaxValueOnTdr

|Value|Meaning|
|--- |--- |
|TRUE|Instructs the GPU scheduler to bypass the aforementioned signaling of the monitored fence to the maximum value in TDR cases.|
|FALSE|The GPU scheduler will signal the monitored fence to the maximum value when a device that can potentially signal it is affected by the GPU reset (TDR).|
 

Supported starting with Windows 10.


### -field NoGPUAccess

 


### -field Reserved

This member is reserved and should be set to zero.


### -field D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS_RESERVED0

This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field Value

[in] A member in the union that is contained in <b>D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</b> that can hold one 32-bit value that identifies attributes of a synchronization object.


## -remarks



Objects to be shared by using the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780251">D3DKMTShareObjects</a> function must first be created with the <b>NtSecuritySharing</b> flag value set. This flag value is available in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547802">D3DKMT_CREATEALLOCATIONFLAGS</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh780254">D3DKMT_CREATEKEYEDMUTEX2_FLAGS</a>, and <b>D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</b> structures.

Drivers should follow these guidelines on <b>D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</b> flags:

<ul>
<li>If the synchronization object is not shared, set both  <b>Shared</b> and <b>NtSecuritySharing</b> to 0.</li>
<li>If the synchronization object is shared with a <b>D3DKMT_HANDLE</b> data type, set <b>Shared</b> = 1 and <b>NtSecuritySharing</b> = 0.</li>
<li>If the synchronization object is shared with an NT handle to the process (and without a global <b>D3DKMT_HANDLE</b> kernel-mode handle to the resource), set <b>Shared</b> = 1 and <b>NtSecuritySharing</b> = 1.</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544658">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544662">D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780251">D3DKMTShareObjects</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547802">D3DKMT_CREATEALLOCATIONFLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780254">D3DKMT_CREATEKEYEDMUTEX2_FLAGS</a>
 

 

