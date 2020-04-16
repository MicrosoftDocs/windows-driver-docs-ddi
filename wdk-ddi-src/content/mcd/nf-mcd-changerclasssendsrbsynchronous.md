---
UID: NF:mcd.ChangerClassSendSrbSynchronous
title: ChangerClassSendSrbSynchronous function (mcd.h)
description: The ChangerClassSendSrbSynchronous routine synchronously sends an SRB to a specified device.
old-location: storage\changerclasssendsrbsynchronous.htm
tech.root: storage
ms.assetid: 6765d7d5-528f-42c5-98c3-0484608a020b
ms.date: 03/29/2018
keywords: ["ChangerClassSendSrbSynchronous function"]
ms.keywords: ChangerClassSendSrbSynchronous, ChangerClassSendSrbSynchronous routine [Storage Devices], chgrclas_ad6fe2cb-20f1-404d-ad08-5bf9798de6bd.xml, mcd/ChangerClassSendSrbSynchronous, storage.changerclasssendsrbsynchronous
f1_keywords:
 - "mcd/ChangerClassSendSrbSynchronous"
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
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
req.lib: Mcd.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Mcd.lib
- Mcd.dll
api_name:
- ChangerClassSendSrbSynchronous
product:
- Windows
targetos: Windows
req.typenames: 
---

# ChangerClassSendSrbSynchronous function


## -description


The <b>ChangerClassSendSrbSynchronous</b> routine synchronously sends an SRB to a specified device.


## -parameters




### -param DeviceObject [in]

Pointer to the functional device object of the target device. 


### -param Srb [in]

Pointer to a partially initialized SCSI request block (SRB) to be sent to the target device. 


### -param Buffer [in]

Specifies address of the buffer that <i>Srb-></i><b>DataBuffer</b> should point to. <b>ChangerClassSendSrbSynchronous</b> creates an MDL for this buffer and passes it to the target device driver in the SRB IRP.


### -param BufferSize [in]

Specifies length, in bytes, of the buffer. 


### -param WriteToDevice [in]

Indicates a write operation when <b>TRUE</b> and read operation when <b>FALSE</b>. 


## -returns



Returns STATUS_SUCCESS if the SRB is transmitted successfully or the appropriate error code if the SRB fails or cannot be sent for some reason. 




## -remarks



Changer miniclass drivers can call this class driver routine in Microsoft Windows XP and later operating systems. Miniclass drivers should use this routine to send an SRB to the port driver instead of calling the <i>classpnp.sys</i> library routine <b>ClassSendSrbSynchronous</b> directly. Although <i>classpnp.sys </i>is shipped with the Windows Driver Kit (WDK), it is not a supported API, and drivers that call this library's routines directly might not function properly in future releases. 

<b>ChangerClassSendSrbSynchronous</b> finishes the initialization of the partially initialized SRB, setting the SRB's flags with the values indicated in the target's device object. <b>ChangerClassSendSrbSynchronous</b> creates the IRP that is used to convey the SRB to the target device, sends the IRP, then handles the IRP's completion. 

If the IRP fails and the sense request data indicates that the IRP should be retried, <b>ChangerClassSendSrbSynchronous</b> will resend the IRP. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>
 

 

