---
UID: NF:irb.AtaPortRegistryControllerKeyWriteDeferred
title: AtaPortRegistryControllerKeyWriteDeferred function
author: windows-driver-content
description: The AtaPortRegistryControllerKeyWriteDeferred routine writes the data asynchronously to the indicated value name under the registry key HKLM\CurrentControlSet\Services\&lt;service name&gt;\ControllerN, where N is the number of the controller.
old-location: storage\ataportregistrycontrollerkeywritedeferred.htm
old-project: storage
ms.assetid: f4297e91-06ae-4c7a-87bc-12e3f5b0238c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: irb/AtaPortRegistryControllerKeyWriteDeferred, AtaPortRegistryControllerKeyWriteDeferred, atartns_cd43ce27-787a-4ffb-99d5-de7f410c4b32.xml, AtaPortRegistryControllerKeyWriteDeferred routine [Storage Devices], storage.ataportregistrycontrollerkeywritedeferred
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: irb.h
req.include-header: Ata.h, Irb.h
req.target-type: Desktop
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	irb.h
apiname:
-	AtaPortRegistryControllerKeyWriteDeferred
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortRegistryControllerKeyWriteDeferred function


## -description


The <b>AtaPortRegistryControllerKeyWriteDeferred</b> routine writes the data asynchronously to the indicated value name under the registry key <b>HKLM\CurrentControlSet\Services\</b><i>&lt;service name&gt;</i><b>\Controller</b><i>N</i>, where <i>N </i>is the number of the controller. 
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
BOOLEAN __inline AtaPortRegistryControllerKeyWriteDeferred(
  _In_ PVOID  ChannelExtension,
  _In_ UCHAR  ControllerNumber,
  _In_ PCHAR  ValueName,
  _In_ UCHAR  ValueType,
  _In_ PUCHAR Buffer,
  _In_ PULONG Length
);
````


## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension. 


### -param ControllerNumber [in]

Contains the controller number. 


### -param ValueName [in]

Contains the name of the registry value to write to. 


### -param ValueType [in]

Indicates the type of data that is contained in the registry value. This member should be assigned one of values indicated in the following table. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
IDE_REG_DWORD

</td>
<td>
A 4-byte numeric value. 

</td>
</tr>
<tr>
<td>
IDE_REG_BINARY

</td>
<td>
Binary data. 

</td>
</tr>
<tr>
<td>
IDE_REG_SZ

</td>
<td>
A null-terminated, Unicode string. 

</td>
</tr>
</table>
 


### -param Buffer [in]

A pointer to the source buffer that contains the data to write to the registry value. 


### -param BufferLength

TBD




#### - Length [in]

A pointer to the number of bytes of data to copy. If the operation fails, the location pointed to by <i>Length</i> will update to the length of data that was successfully copied to the registry.


## -returns



<b>AtaPortRegistryControllerKeyWriteDeferred</b> returns <b>TRUE</b> if the operation succeeds. Otherwise, it returns <b>FALSE</b>. The routine also returns <b>FALSE</b> if the miniport driver does not call it from the correct routine. 




## -remarks



If the value name is not present, the <b>AtaPortRegistryControllerKeyWriteDeferred</b> routine creates an entry for the value name and stores the input data under the newly created value name. 

The miniport driver can call the <b>AtaPortRegistryControllerKeyWriteDeferred</b> routine from any of the routines that are defined in the channel interface. 

The buffer pointed to by <i>Buffer </i>must be allocated by using <a href="..\irb\nf-irb-ataportregistryallocatebuffer.md">AtaPortRegistryAllocateBuffer</a>. The miniport driver must not reuse this buffer after it calls <b>AtaPortRegistryControllerKeyWriteDeferred</b> because the port driver delays writing the key data. If the miniport driver reuses the buffer, it might overwrite the data in the buffer before the port driver has an opportunity to store it in the registry key. The port driver flushes the buffer when the miniport driver calls <a href="..\irb\nf-irb-ataportregistryfreebuffer.md">AtaPortRegistryFreeBuffer</a> to free the buffer. 




## -see-also

<a href="..\irb\nf-irb-ataportregistryfreebuffer.md">AtaPortRegistryFreeBuffer</a>



<a href="..\irb\nf-irb-ataportregistryallocatebuffer.md">AtaPortRegistryAllocateBuffer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortRegistryControllerKeyWriteDeferred routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

