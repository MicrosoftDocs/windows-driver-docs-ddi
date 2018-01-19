---
UID: NC:irb.IDE_HW_BUILDIO
title: IDE_HW_BUILDIO
author: windows-driver-content
description: The IdeHwBuildIo miniport driver routine is called one time for every incoming I/O request.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\idehwbuildio.htm
old-project: storage
ms.assetid: 057fb78f-6f1c-4b16-b9fa-6fcff299a90d
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
req.alt-api: IdeHwBuildIo
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

# IDE_HW_BUILDIO callback



## -description
The <b><i>IdeHwBuildIo</i></b> miniport driver routine is called one time for every incoming I/O request.



## -prototype

````
IDE_HW_BUILDIO IdeHwBuildIo;

BOOLEAN IdeHwBuildIo(
  _In_ PVOID              ChannelExtension,
  _In_ PIDE_REQUEST_BLOCK Irb
)
{ ... }
````


## -parameters

### -param ChannelExtension [in]

A pointer to the miniport driver channel extension.


### -param Irb [in]

A pointer to a structure of type <a href="..\irb\ns-irb-_ide_request_block.md">IDE_REQUEST_BLOCK</a> that defines the Integrated Device Electronics (IDE) input/output request block (IRB) to process.


## -returns
<b><i>IdeHwBuildIo</i></b> returns <b>TRUE</b> to acknowledge the receipt of the <a href="..\irb\ns-irb-_ide_request_block.md">IDE_REQUEST_BLOCK</a> structure. The port driver ignores a return value of <b>FALSE</b>.


## -remarks
Miniport drivers provide an <b><i>AtaHwBuildlo</i></b> routine that performs unsynchronized I/O processing with interrupts enabled. After <b><i>IdeHwBuildIo</i></b> completes all unsynchronized processing of a request, it returns to the port driver, and the port driver passes the request to the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff559003">IdeHwStartIo</a> routine, which performs the tasks that require synchronization. 

The miniport driver must observe certain restrictions while it executes the <b><i>IdeHwBuildIo</i></b> routine. The miniport driver calls <b><i>IdeHwBuildIo</i></b> without holding any locks. In particular, the miniport driver must not touch any shared data in its channel extension, nor can it call any of the routines exported by the ATA port driver.

If the miniport driver must complete a request while it executes the <b><i>IdeHwBuildIo</i></b> routine, it must assign the appropriate completion status value to the <b>IrbStatus</b> member of the <a href="..\irb\ns-irb-_ide_request_block.md">IDE_REQUEST_BLOCK</a> structure pointed to by the <i>Irb</i> parameter. The miniport driver must not set <b>IrbStatus</b> to a value of IRB_STATUS_PENDING.

The miniport driver can use the <b><i>IdeHwBuildIo</i></b> routine to indicate to the port driver how an IRB should be handled. For example, the miniport driver can request that the port driver map the buffer at <i>DataBuffer </i>by setting the <b>IrbFlags</b> member of the IRB to the appropriate value. The miniport driver should not request that the buffer that is associated with a request be mapped unless the request is some type of data transfer. 

The <b><i>IdeHwBuildIo</i></b> routine resembles Storport's <a href="..\storport\nc-storport-hw_buildio.md">HwStorBuildIo</a> routine in functionality. For more information about the <b><i>HwStorBuildIo</i></b> routine, see <a href="https://msdn.microsoft.com/6b18e3ff-30dd-414b-99b5-4bb914660a67">Unsynchronized HwStorBuildIo Routine</a>.

<b><i>IdeHwBuildIo</i></b> is an optional routine.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559003">IdeHwStartIo</a>
</dt>
<dt>
<a href="..\irb\ns-irb-_ide_request_block.md">IDE_REQUEST_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IdeHwBuildIo routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

