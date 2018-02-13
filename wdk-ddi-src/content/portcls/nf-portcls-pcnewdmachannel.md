---
UID: NF:portcls.PcNewDmaChannel
title: PcNewDmaChannel function
author: windows-driver-content
description: The PcNewDmaChannel function creates a new DMA-channel object. This function is obsolete; for more information, see the following comments.
old-location: audio\pcnewdmachannel.htm
old-project: audio
ms.assetid: 4a3a39ac-0db9-48a9-8da6-c2b914fa1de6
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.pcnewdmachannel, PcNewDmaChannel function [Audio Devices], PcNewDmaChannel, portcls/PcNewDmaChannel, audpc-routines_51deae73-e4dd-4b39-ae73-77cf31f8ec06.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Portcls.lib
-	Portcls.dll
apiname:
-	PcNewDmaChannel
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# PcNewDmaChannel function


## -description


The <b>PcNewDmaChannel</b> function creates a new DMA-channel object. This function is obsolete; for more information, see the following comments.


## -syntax


````
NTSTATUS PcNewDmaChannel(
  _Out_    PDMACHANNEL         *OutDmaChannel,
  _In_opt_ PUNKNOWN            OuterUnknown,
  _In_     POOL_TYPE           PoolType,
  _In_     PDEVICE_DESCRIPTION DeviceDescription,
  _In_     PDEVICE_OBJECT      DeviceObject
);
````


## -parameters




### -param OutDmaChannel [out]

Output pointer for the DMA-channel object created by this function. This parameter points to a caller-allocated pointer variable into which the function outputs a reference to the newly created <a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a> object. Specify a valid, non-<b>NULL</b> pointer value for this parameter.


### -param OuterUnknown [in, optional]

Pointer to the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface of an object that needs to aggregate the object. Unless aggregation is required, set this parameter to <b>NULL</b>.


### -param PoolType [in]

Specifies the type of storage pool from which the object is to be allocated. This is a <a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a> enumeration value. Specify a nonpaged pool type for this parameter.


### -param DeviceDescription [in]

Pointer to a description of the physical device for which the caller is requesting a DMA object. This parameter points to a structure of type <a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a>.


### -param DeviceObject [in]

Pointer to the device object for the physical adapter device. This parameter points to a system structure of type <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>.


## -returns



<b>PcNewDmaChannel</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



<b>PcNewDmaChannel</b> is obsolete. For all new audio drivers, use one of the following IPortWave <i>Xxx</i>::New<i>Xxx</i>DmaChannel methods in place of <b>PcNewDmaChannel</b>:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff536916">IPortWavePci::NewMasterDmaChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536900">IPortWaveCyclic::NewMasterDmaChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536902">IPortWaveCyclic::NewSlaveDmaChannel</a>


For the sake of backward compatibility, the PortCls system driver will continue to support <b>PcNewDmaChannel</b>, and existing drivers can continue to use this function. For more information, see <a href="https://msdn.microsoft.com/0497acff-1e7f-45b9-b5ec-f1783ea7e900">DirectSound Hardware Acceleration in 64-Bit Versions of Windows XP</a>.

Specify the <i>PoolType</i> parameter to be one of the nonpaged pool types defined in the POOL_TYPE enumeration. The DMA-channel object must not reside in paged memory because several of the methods in the <a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a> interface can be called from IRQL DISPATCH_LEVEL.

The <i>OutDmaChannel</i> and <i>OuterUnknown </i>parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also

<a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a>



<a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcNewDmaChannel function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

