---
UID: NC:irb.IDE_HW_STARTIO
title: IDE_HW_STARTIO
author: windows-driver-content
description: The IdeHwStartIo miniport driver routine processes the synchronized aspects of an I/O request.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\idehwstartio.htm
old-project: storage
ms.assetid: 9172e62e-263c-471c-bcc2-9be4e1d6b1a2
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: WdmlibIoGetAffinityInterrupt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: irb.h
req.include-header: Irb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IdeHwStartIo
req.alt-loc: irb.h
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
req.typenames: LUID
---

# IDE_HW_STARTIO callback



## -description
The <b><i>IdeHwStartIo</i></b> miniport driver routine processes the synchronized aspects of an I/O request.



## -prototype

````
IDE_HW_STARTIO IdeHwStartIo;

BOOLEAN IdeHwStartIo(
  _In_ PVOID              ChannelExtension,
  _In_ PIDE_REQUEST_BLOCK Irb
)
{ ... }
````


## -parameters

### -param ChannelExtension [in]

A pointer to the miniport driver per channel device extension.


### -param Irb [in]

A pointer to a structure of type <a href="..\irb\ns-irb-_ide_request_block.md">IDE_REQUEST_BLOCK</a> that defines the IDE request block (IRB) to process.


## -returns
<b><i>IdeHwStartIo</i></b> returns <b>TRUE</b> to acknowledge the receipt of an IRB. The port driver ignores a return value of <b>FALSE</b>.


## -remarks
Miniport drivers must provide an <b><i>IdeHwStartIo</i></b> routine to process the aspects of an I/O request that must be handled synchronously. For information about how the miniport driver processes the unsynchronized aspects of an I/O request, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557462">IdeHwBuildIo</a>. 

After the miniport driver receives the <b><i>IdeHwStartIo</i></b> call, it owns the request and must complete it.

After this routine returns, the miniport driver should be prepared to receive the next request from the port driver immediately. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557462">IdeHwBuildIo</a>
</dt>
<dt>
<a href="..\irb\ns-irb-_ide_request_block.md">IDE_REQUEST_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IdeHwStartIo routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

