---
UID: NF:bdasup.BdaCreateTopology
title: BdaCreateTopology function
author: windows-driver-content
description: The BdaCreateTopology function creates the topology between two pins.
old-location: stream\bdacreatetopology.htm
tech.root: stream
ms.assetid: 855ef77c-2a85-4c8c-b8e3-c4aaa0d2a089
ms.date: 4/23/2018
ms.keywords: BdaCreateTopology, BdaCreateTopology function [Streaming Media Devices], bdaref_bbf47d95-2b93-4e05-a5fa-aa5ed4968b0a.xml, bdasup/BdaCreateTopology, stream.bdacreatetopology
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
-	BdaCreateTopology
product:
- Windows
targetos: Windows
req.typenames: 
---

# BdaCreateTopology function


## -description


The <b>BdaCreateTopology</b> function creates the topology between two pins. 


## -parameters




### -param pKSFilter [in]

Points to the BDA filter on which to create topology.


### -param InputPinId [in]

Specifies the identifier of the filter's input pin.


### -param OutputPinId [in]

Specifies the identifier of the filter's output pin.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. Returns <b>NULL</b> if no valid pin pairing exists with the specified input and output pins. 






## -remarks



A BDA minidriver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556471">BdaMethodCreateTopology</a> function when the network provider dynamically creates a topology between filter pins using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563413">KSMETHOD_BDA_CREATE_TOPOLOGY</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a> method set. If a BDA minidriver must create a topology between filter pins without relying on the network provider, the BDA minidriver should call the <b>BdaCreateTopology</b> function directly.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556471">BdaMethodCreateTopology</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563413">KSMETHOD_BDA_CREATE_TOPOLOGY</a>
 

 

