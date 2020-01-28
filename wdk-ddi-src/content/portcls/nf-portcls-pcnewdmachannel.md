---
UID: NF:portcls.PcNewDmaChannel
title: PcNewDmaChannel function (portcls.h)
description: The PcNewDmaChannel function creates a new DMA-channel object. This function is obsolete; for more information, see the following comments.
old-location: audio\pcnewdmachannel.htm
tech.root: audio
ms.assetid: 4a3a39ac-0db9-48a9-8da6-c2b914fa1de6
ms.date: 05/08/2018
ms.keywords: PcNewDmaChannel, PcNewDmaChannel function [Audio Devices], audio.pcnewdmachannel, audpc-routines_51deae73-e4dd-4b39-ae73-77cf31f8ec06.xml, portcls/PcNewDmaChannel
f1_keywords:
 - "portcls/PcNewDmaChannel"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Obsolete. For all new audio drivers, use a IPortWaveXxx::NewXxxDmaChannel method instead. The PortCls system driver implements the PcNewDmaChannel function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
- PcNewDmaChannel
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcNewDmaChannel function


## -description


The <b>PcNewDmaChannel</b> function creates a new DMA-channel object. This function is obsolete; for more information, see the following comments.


## -parameters




### -param OutDmaChannel [out]

Output pointer for the DMA-channel object created by this function. This parameter points to a caller-allocated pointer variable into which the function outputs a reference to the newly created <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-idmachannel">IDmaChannel</a> object. Specify a valid, non-<b>NULL</b> pointer value for this parameter.


### -param OuterUnknown [in, optional]

Pointer to the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface of an object that needs to aggregate the object. Unless aggregation is required, set this parameter to <b>NULL</b>.


### -param PoolType [in]

Specifies the type of storage pool from which the object is to be allocated. This is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a> enumeration value. Specify a nonpaged pool type for this parameter.


### -param DeviceDescription [in]

Pointer to a description of the physical device for which the caller is requesting a DMA object. This parameter points to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_description">DEVICE_DESCRIPTION</a>.


### -param DeviceObject [in]

Pointer to the device object for the physical adapter device. This parameter points to a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.


## -returns



<b>PcNewDmaChannel</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



<b>PcNewDmaChannel</b> is obsolete. For all new audio drivers, use one of the following IPortWave <i>Xxx</i>::New<i>Xxx</i>DmaChannel methods in place of <b>PcNewDmaChannel</b>:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavepci-newmasterdmachannel">IPortWavePci::NewMasterDmaChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavecyclic-newmasterdmachannel">IPortWaveCyclic::NewMasterDmaChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavecyclic-newslavedmachannel">IPortWaveCyclic::NewSlaveDmaChannel</a>


For the sake of backward compatibility, the PortCls system driver will continue to support <b>PcNewDmaChannel</b>, and existing drivers can continue to use this function.

Specify the <i>PoolType</i> parameter to be one of the nonpaged pool types defined in the POOL_TYPE enumeration. The DMA-channel object must not reside in paged memory because several of the methods in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-idmachannel">IDmaChannel</a> interface can be called from IRQL DISPATCH_LEVEL.

The <i>OutDmaChannel</i> and <i>OuterUnknown </i>parameters follow the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/reference-counting-conventions-for-com-objects">reference-counting conventions for COM objects</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_description">DEVICE_DESCRIPTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-idmachannel">IDmaChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a>
 

 

