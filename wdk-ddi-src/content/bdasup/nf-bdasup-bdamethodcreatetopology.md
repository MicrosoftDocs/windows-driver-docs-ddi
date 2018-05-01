---
UID: NF:bdasup.BdaMethodCreateTopology
title: BdaMethodCreateTopology function
author: windows-driver-content
description: The BdaMethodCreateTopology function creates a template topology between two pins of a filter.
old-location: stream\bdamethodcreatetopology.htm
old-project: stream
ms.assetid: 1f0e8fdc-ae3d-4f5e-b047-b3b7bf73d389
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: BdaMethodCreateTopology, BdaMethodCreateTopology function [Streaming Media Devices], bdaref_3e082bad-4178-430a-aca0-3af6324a0aa2.xml, bdasup/BdaMethodCreateTopology, stream.bdamethodcreatetopology
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Bdasup.lib
-	Bdasup.dll
api_name:
-	BdaMethodCreateTopology
product: Windows
targetos: Windows
req.typenames: 
---

# BdaMethodCreateTopology function


## -description


The <b>BdaMethodCreateTopology</b> function creates a template topology between two pins of a filter. 


## -parameters




### -param pIrp

TBD


### -param pKSMethod [in]

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a> structure that describes the method and request type of a method request.


### -param pvIgnored [optional]

Points to a buffer that is ignored. 


#### - Irp [in]

Points to the IRP for the request to create topology. The BDA minidriver receives this IRP with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563413">KSMETHOD_BDA_CREATE_TOPOLOGY</a> request.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaMethodCreateTopology</b> function to create the template topology between two filter pins after the minidriver receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563413">KSMETHOD_BDA_CREATE_TOPOLOGY</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a> method set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaMethodCreateTopology</b> function directly. Some BDA minidrivers must intercept this request, using an internal method (<a href="https://msdn.microsoft.com/library/windows/hardware/ff567191">KStrMethodHandler</a>), rather than dispatch it directly. These mindrivers must obtain a pointer to the BDA filter from the passed IRP before calling <b>BdaMethodCreateTopology</b> so that they can use the filter to keep track of associated pins. These mindrivers can then send instructions to the hardware when connecting particular pin types. See <a href="https://msdn.microsoft.com/1c0dace6-b618-4705-bf5d-65457d14c072">Defining Automation Tables</a> and <a href="https://msdn.microsoft.com/4af9efc3-8073-4111-9ad0-8b2fba4d1545">Configuring a BDA Filter</a> for more information. 

If a BDA minidriver must create the template topology between two filter pins without relying on the network provider, the BDA minidriver should call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556448">BdaCreateTopology</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556448">BdaCreateTopology</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563413">KSMETHOD_BDA_CREATE_TOPOLOGY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567191">KStrMethodHandler</a>
 

 

