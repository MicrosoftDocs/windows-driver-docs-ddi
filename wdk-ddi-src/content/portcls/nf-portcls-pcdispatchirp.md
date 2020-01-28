---
UID: NF:portcls.PcDispatchIrp
title: PcDispatchIrp function (portcls.h)
description: The PcDispatchIrp function dispatches an IRP to the PortCls system driver's default handler.
old-location: audio\pcdispatchirp.htm
tech.root: audio
ms.assetid: 01add66e-a007-4b1d-add6-c5be71dd0d61
ms.date: 05/08/2018
ms.keywords: PcDispatchIrp, PcDispatchIrp function [Audio Devices], audio.pcdispatchirp, audpc-routines_c87193c2-a8f8-4ba1-bf47-422fb5ff452d.xml, portcls/PcDispatchIrp
f1_keywords:
 - "portcls/PcDispatchIrp"
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcDispatchIrp function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
- PcDispatchIrp
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcDispatchIrp function


## -description


The <b>PcDispatchIrp</b> function dispatches an IRP to the PortCls system driver's default handler.


## -parameters




### -param pDeviceObject [in]

Pointer to the device object. This parameter must point to a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.


### -param pIrp [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> that is to be dispatched


## -returns



<b>PcDispatchIrp</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



As part of its initialization process, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcinitializeadapterdriver">PcInitializeAdapterDriver</a> function loads pointers to handlers for several IRPs into the driver object. Following the call to <b>PcInitializeAdapterDriver</b>, an adapter driver can choose to overwrite one or more of the PortCls handler pointers with pointers to its own IRP handlers.

If, after receiving an IRP, the adapter driver's IRP handler determines that the IRP should be handled by the PortCls IRP handler instead, the adapter driver's handler calls <b>PcDispatchIrp</b> to forward the IRP to the PortCls handler.

For a code example, see the SB16 sample audio driver in the Microsoft Windows Driver Kit (WDK). 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcinitializeadapterdriver">PcInitializeAdapterDriver</a>
 

 

