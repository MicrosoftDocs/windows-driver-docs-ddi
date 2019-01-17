---
UID: NF:portcls.IPortWavePci.NewMasterDmaChannel
title: IPortWavePci::NewMasterDmaChannel
description: The NewMasterDmaChannel method creates a new instance of a bus-master DMA channel.
old-location: audio\iportwavepci_newmasterdmachannel.htm
tech.root: audio
ms.assetid: a4128541-1982-413d-a013-422ca1cf4542
ms.date: 05/08/2018
ms.keywords: IPortWavePci interface [Audio Devices],NewMasterDmaChannel method, IPortWavePci.NewMasterDmaChannel, IPortWavePci::NewMasterDmaChannel, NewMasterDmaChannel, NewMasterDmaChannel method [Audio Devices], NewMasterDmaChannel method [Audio Devices],IPortWavePci interface, audio.iportwavepci_newmasterdmachannel, audmp-routines_01c562e8-f0b7-4232-9595-2312175c097f.xml, portcls/IPortWavePci::NewMasterDmaChannel
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPortWavePci.NewMasterDmaChannel
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortWavePci::NewMasterDmaChannel


## -description


The <code>NewMasterDmaChannel</code> method creates a new instance of a bus-master DMA channel.


## -parameters




### -param OutDmaChannel




### -param OuterUnknown [in, optional]

Pointer to the <b>IUnknown</b> interface of an object that needs to aggregate the DMA-channel object. This parameter is optional. If aggregation is not required, specify this parameter as <b>NULL</b>.


### -param PoolType [in]

Specifies the type of storage pool from which the object is to be allocated. This is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a> enumeration value. Specify a nonpaged pool type for this parameter.


### -param ResourceList [in, optional]

Pointer to the miniport driver's resource list, which is an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a> object. This parameter is optional and can be specified as <b>NULL</b>. The <code>NewMasterDmaChannel</code> method currently makes no use of this parameter.


### -param ScatterGather [in]

Requests that the DMA channel support scatter/gather DMA. Always set this parameter to <b>TRUE</b>.


### -param Dma32BitAddresses [in]

Specifies the use of 32-bit addresses for DMA operations.


### -param Dma64BitAddresses [in]

Specifies the use of 64-bit addresses for DMA operations.


### -param IgnoreCount [in]

Indicates whether to ignore the DMA controller's transfer counter. Set to <b>TRUE</b> if the DMA controller in this platform does not maintain an accurate transfer counter, and therefore requires a workaround.


### -param DmaWidth [in]

Not used. Set to (DMA_WIDTH)(-1).


### -param DmaSpeed [in]

Not used. Set to (DMA_SPEED)(-1).


### -param MaximumLength [in]

Maximum number of bytes in the buffer that will be associated with this DMA channel.


### -param DmaPort [in]

Not used. Set to 0.


#### - DmaChannel [out]

Output pointer for the DMA channel. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the new DMA-channel object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536547">IDmaChannel</a> interface.


## -returns



<code>NewMasterDmaChannel</code> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



The definitions of the call parameters for the <code>NewMasterDmaChannel</code> method are similar to those for the members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543107">DEVICE_DESCRIPTION</a> structure with the same names.

Specify the <i>PoolType</i> parameter to be one of the nonpaged pool types defined in the POOL_TYPE enumeration. The DMA-channel object must not reside in paged memory because several of the methods in the <b>IDmaChannel</b> interface can be called from IRQL DISPATCH_LEVEL.

The <i>DmaChannel</i>, <i>OuterUnknown</i>, and <i>ResourceList</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543107">DEVICE_DESCRIPTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536547">IDmaChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536905">IPortWavePci</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a>
 

 

