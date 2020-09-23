---
UID: NF:portcls.PcCompleteIrp
title: PcCompleteIrp function (portcls.h)
description: The PcCompleteIrp function completes an IRP that was previously marked as pending.
old-location: audio\pccompleteirp.htm
tech.root: audio
ms.assetid: fa0b36bf-0628-4136-9ca7-1d20823969ff
ms.date: 05/08/2018
keywords: ["PcCompleteIrp function"]
ms.keywords: PcCompleteIrp, PcCompleteIrp function [Audio Devices], audio.pccompleteirp, audpc-routines_f61145f8-9e55-4b2a-a3aa-37f7be4f4df3.xml, portcls/PcCompleteIrp
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcCompleteIrp function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PcCompleteIrp
 - portcls/PcCompleteIrp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Portcls.lib
 - Portcls.dll
api_name:
 - PcCompleteIrp
---

# PcCompleteIrp function


## -description

The <b>PcCompleteIrp</b> function completes an IRP that was previously marked as pending.

## -parameters

### -param pDeviceObject 

[in]
Pointer to the device object for the device. This parameter must point to a system structure of type <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.

### -param pIrp 

[in]
Pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> that is to be completed

### -param ntStatus 

[in]
Specifies the status of the completed IRP. See the list of NTSTATUS values defined in header file ntstatus.h.

## -returns

<b>PcCompleteIrp</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks

<b>PcCompleteIrp</b> is used when an IRP handler returns STATUS_PENDING and the IRP must later be completed. When the adapter driver finishes all processing of the IRP, it calls <b>PcCompleteIrp</b> to complete the IRP.

The IRP handler should not call this function. An adapter driver's IRP handler instead calls <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcdispatchirp">PcDispatchIrp</a> to pass the IRP to the PortCls system driver's IRP handler to perform all remaining processing of the IRP.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcdispatchirp">PcDispatchIrp</a>