---
UID: NF:irb.AtaPortRegistryChannelSubkeyWriteDeferred
title: AtaPortRegistryChannelSubkeyWriteDeferred function
author: windows-driver-content
description: The AtaPortRegistryChannelSubKeyWriteDeferred routine writes data asynchronously to the indicated value name under the registry key HKLM\CurrentControlSet\Services\&lt;service name&gt;\ControllerN\ChannelM, where N is the number of the controller and M is the number of the channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\ataportregistrychannelsubkeywritedeferred.htm
old-project: storage
ms.assetid: 332f6921-1ad2-42ae-9728-001f243b8cff
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AtaPortRegistryChannelSubkeyWriteDeferred, AtaPortRegistryChannelSubkeyWriteDeferred routine [Storage Devices], atartns_ddf14e05-c641-4382-88b4-18abb54e0f17.xml, irb/AtaPortRegistryChannelSubkeyWriteDeferred, storage.ataportregistrychannelsubkeywritedeferred
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	irb.h
api_name:
-	AtaPortRegistryChannelSubkeyWriteDeferred
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortRegistryChannelSubkeyWriteDeferred function


## -description


The <b>AtaPortRegistryChannelSubKeyWriteDeferred</b> routine writes data asynchronously to the indicated value name under the registry key <b>HKLM\CurrentControlSet\Services\</b><i>&lt;service name&gt;</i><b>\Controller</b><i>N</i>\<b>Channel</b><i>M</i>, where <i>N </i>is the number of the controller and <i>M </i>is the number of the channel.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

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
A null-terminated. Unicode string. 

</td>
</tr>
</table>
 


### -param Buffer [in]

Pointer to the source buffer that contains the data to be written to the registry. 


### -param BufferLength

TBD




#### - Length [in]

A pointer to the number of bytes of data to copy. If the operation fails, the location that is pointed to by <i>Length</i> will update to the length of the data that was successfully written to the registry.


## -returns



<b>AtaPortRegistryChannelSubKeyWriteDeferred</b> returns <b>TRUE</b> if the operation. Otherwise, it returns <b>FALSE</b>. The routine also returns <b>FALSE</b> if the miniport driver does not call it from the correct routine.




## -remarks



If the value name is not present, <b>AtaPortRegistryChannelSubKeyWriteDeferred</b> creates an entry for the value and the data is stored in the newly created value. 

The buffer that is pointed to by <i>Buffer </i>must be allocated by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff550200">AtaPortRegistryAllocateBuffer</a>. 

The miniport driver can call <b>AtaPortRegistryChannelSubKeyWriteDeferred</b> from any of the key routines that belong to its channel interface. 

The miniport driver must not reuse the buffer that is pointed to by <i>Buffer</i> after the initial call to <b>AtaPortRegistryChannelSubKeyWriteDeferred</b>. Because the call is asynchronous, <i>Buffer</i> might still point to data that has not been flushed to the registry. The port driver flushes the data in the buffer to the registry when the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550212">AtaPortRegistryFreeBuffer</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550200">AtaPortRegistryAllocateBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550212">AtaPortRegistryFreeBuffer</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortRegistryChannelSubKeyWriteDeferred routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

