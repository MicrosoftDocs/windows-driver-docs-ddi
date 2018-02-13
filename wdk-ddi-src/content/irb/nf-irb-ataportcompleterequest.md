---
UID: NF:irb.AtaPortCompleteRequest
title: AtaPortCompleteRequest function
author: windows-driver-content
description: The AtaPortCompleteRequest routine completes the indicated IRB.
old-location: storage\ataportcompleterequest.htm
old-project: storage
ms.assetid: 2dddd012-9a13-49e4-9392-300938e78609
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: irb/AtaPortCompleteRequest, AtaPortCompleteRequest, AtaPortCompleteRequest routine [Storage Devices], atartns_6ed3a9ca-b9b8-4d2f-a2f2-5a57db2071f8.xml, storage.ataportcompleterequest
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
req.lib: Ataport.lib; Pciidex.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ataport.lib
-	ataport.dll
-	pciidex.lib
-	pciidex.dll
apiname:
-	AtaPortCompleteRequest
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortCompleteRequest function


## -description


The <b>AtaPortCompleteRequest</b> routine completes the indicated IRB. 
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
VOID AtaPortCompleteRequest(
  _In_ PVOID              ChannelExtension,
  _In_ PIDE_REQUEST_BLOCK Irb
);
````


## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension.


### -param Irb [in]

A pointer to a structure of type <a href="..\irb\ns-irb-_ide_request_block.md">IDE_REQUEST_BLOCK</a> that defines the IDE request block (IRB) to be completed.


## -returns



None 




## -remarks



The miniport driver uses this routine to indicate to the port driver that the IRB has completed. The miniport driver must not touch the IRB after this call. It is an error to complete an IRB with status IRB_STATUS_PENDING.




## -see-also

<a href="..\irb\ns-irb-_ide_request_block.md">IDE_REQUEST_BLOCK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortCompleteRequest routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

