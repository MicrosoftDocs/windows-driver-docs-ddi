---
UID: NF:bdasup.BdaMethodCreateTopology
title: BdaMethodCreateTopology function (bdasup.h)
description: The BdaMethodCreateTopology function creates a template topology between two pins of a filter.
old-location: stream\bdamethodcreatetopology.htm
tech.root: stream
ms.assetid: 1f0e8fdc-ae3d-4f5e-b047-b3b7bf73d389
ms.date: 04/23/2018
ms.keywords: BdaMethodCreateTopology, BdaMethodCreateTopology function [Streaming Media Devices], bdaref_3e082bad-4178-430a-aca0-3af6324a0aa2.xml, bdasup/BdaMethodCreateTopology, stream.bdamethodcreatetopology
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
- BdaMethodCreateTopology
product:
- Windows
targetos: Windows
req.typenames: 
---

# BdaMethodCreateTopology function


## -description


The <b>BdaMethodCreateTopology</b> function creates a template topology between two pins of a filter. 


## -parameters




### -param pIrp




### -param pKSMethod [in]

Points to a <a href="https://docs.microsoft.com/previous-versions/ff563398(v=vs.85)">KSMETHOD</a> structure that describes the method and request type of a method request.


### -param pvIgnored [optional]

Points to a buffer that is ignored. 


#### - Irp [in]

Points to the IRP for the request to create topology. The BDA minidriver receives this IRP with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethod-bda-create-topology">KSMETHOD_BDA_CREATE_TOPOLOGY</a> request.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaMethodCreateTopology</b> function to create the template topology between two filter pins after the minidriver receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethod-bda-create-topology">KSMETHOD_BDA_CREATE_TOPOLOGY</a> request of the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethodsetid-bdadeviceconfiguration">KSMETHODSETID_BdaDeviceConfiguration</a> method set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaMethodCreateTopology</b> function directly. Some BDA minidrivers must intercept this request, using an internal method (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnkshandler">KStrMethodHandler</a>), rather than dispatch it directly. These mindrivers must obtain a pointer to the BDA filter from the passed IRP before calling <b>BdaMethodCreateTopology</b> so that they can use the filter to keep track of associated pins. These mindrivers can then send instructions to the hardware when connecting particular pin types. See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/defining-automation-tables">Defining Automation Tables</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/configuring-a-bda-filter">Configuring a BDA Filter</a> for more information. 

If a BDA minidriver must create the template topology between two filter pins without relying on the network provider, the BDA minidriver should call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bdasup/nf-bdasup-bdacreatetopology">BdaCreateTopology</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bdasup/nf-bdasup-bdacreatetopology">BdaCreateTopology</a>



<a href="https://docs.microsoft.com/previous-versions/ff563398(v=vs.85)">KSMETHOD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethodsetid-bdadeviceconfiguration">KSMETHODSETID_BdaDeviceConfiguration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethod-bda-create-topology">KSMETHOD_BDA_CREATE_TOPOLOGY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnkshandler">KStrMethodHandler</a>
 

 

