---
UID: NF:bdasup.BdaMethodCreatePin
title: BdaMethodCreatePin function (bdasup.h)
description: The BdaMethodCreatePin function creates a pin factory.
old-location: stream\bdamethodcreatepin.htm
tech.root: stream
ms.assetid: 0bc31a97-661c-463d-a043-9f86f63bb4b4
ms.date: 04/23/2018
ms.keywords: BdaMethodCreatePin, BdaMethodCreatePin function [Streaming Media Devices], bdaref_492b1847-e4b7-4dfd-a8b1-c6c17fc6aff8.xml, bdasup/BdaMethodCreatePin, stream.bdamethodcreatepin
ms.topic: function
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
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
req.lib: Bdasup.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Bdasup.lib
- Bdasup.dll
api_name:
- BdaMethodCreatePin
product:
- Windows
targetos: Windows
req.typenames: 
---

# BdaMethodCreatePin function


## -description


The <b>BdaMethodCreatePin</b> function creates a pin factory. 


## -parameters




### -param pIrp




### -param pKSMethod [in]

Points to a <a href="https://docs.microsoft.com/previous-versions/ff563398(v=vs.85)">KSMETHOD</a> structure that describes the method and request type of a method request.


### -param pulPinFactoryID [out, optional]

Points to a variable that receives the identifier of the pin factory. 


#### - Irp [in]

Points to the IRP for the request to create a pin factory. The BDA minidriver receives this IRP with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethod-bda-create-pin-factory">KSMETHOD_BDA_CREATE_PIN_FACTORY</a> request.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaMethodCreatePin</b> function to create a pin factory after the minidriver receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethod-bda-create-pin-factory">KSMETHOD_BDA_CREATE_PIN_FACTORY</a> request of the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethodsetid-bdadeviceconfiguration">KSMETHODSETID_BdaDeviceConfiguration</a> method set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaMethodCreatePin</b> function directly, without intercepting this request using an internal method (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnkshandler">KStrMethodHandler</a>). See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/defining-automation-tables">Defining Automation Tables</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/configuring-a-bda-filter">Configuring a BDA Filter</a> for more information. 

If a BDA minidriver must create a pin without relying on the network provider, the BDA minidriver should call the <b>BdaCreatePin</b> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bdasup/nf-bdasup-bdacreatepin">BdaCreatePin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bdasup/nf-bdasup-bdamethoddeletepin">BdaMethodDeletePin</a>



<a href="https://docs.microsoft.com/previous-versions/ff563398(v=vs.85)">KSMETHOD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethodsetid-bdadeviceconfiguration">KSMETHODSETID_BdaDeviceConfiguration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethod-bda-create-pin-factory">KSMETHOD_BDA_CREATE_PIN_FACTORY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnkshandler">KStrMethodHandler</a>
 

 

