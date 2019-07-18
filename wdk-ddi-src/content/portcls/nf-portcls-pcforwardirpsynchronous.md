---
UID: NF:portcls.PcForwardIrpSynchronous
title: PcForwardIrpSynchronous function (portcls.h)
description: The PcForwardIrpSynchronous function is used by IRP handlers to forward Plug and Play IRPs to the physical device object (PDO).
old-location: audio\pcforwardirpsynchronous.htm
tech.root: audio
ms.assetid: 29f69d26-6788-4c52-b6a4-ef96991ea238
ms.date: 05/08/2018
ms.keywords: PcForwardIrpSynchronous, PcForwardIrpSynchronous function [Audio Devices], audio.pcforwardirpsynchronous, audpc-routines_9ecb1bfa-c318-424c-8f65-3777136c5f65.xml, portcls/PcForwardIrpSynchronous
ms.topic: function
f1_keywords:
 - "portcls/PcForwardIrpSynchronous"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcForwardIrpSynchronous function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Portcls.lib
- Portcls.dll
api_name:
- PcForwardIrpSynchronous
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcForwardIrpSynchronous function


## -description


The <b>PcForwardIrpSynchronous</b> function is used by IRP handlers to forward Plug and Play IRPs to the <a href="https://docs.microsoft.com/windows-hardware/drivers/">physical device object (PDO)</a>.


## -parameters




### -param DeviceObject [in]

Pointer to the audio device's device object. This parameter must point to a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.


### -param Irp [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_irp">IRP</a> that is to be forwarded


## -returns



<b>PcForwardIrpSynchronous</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



<b>PcForwardIrpSynchronous</b> causes the next PDO to receive the IRP and block until the IRP has been completed by the physical device driver. At that point, <b>PcForwardIrpSynchronous</b> unblocks and returns to the caller. The caller (an IRP handler) should eventually return--possibly with a status of STATUS_PENDING. In general, any IRP handler that calls this function must specify the action IRP_ACTION_FINISH upon returning. Any other action would result in the IRP being forwarded to the physical device a second time.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pccompleteirp">PcCompleteIrp</a> function is used when an IRP handler returns STATUS_PENDING and the IRP must be completed later.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_irp">IRP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pccompleteirp">PcCompleteIrp</a>
 

 

