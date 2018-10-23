---
UID: NF:bdasup.BdaMethodDeletePin
title: BdaMethodDeletePin function
author: windows-driver-content
description: The BdaMethodDeletePin function deletes a pin factory.
old-location: stream\bdamethoddeletepin.htm
tech.root: stream
ms.assetid: 179419ee-2a99-4c03-9afb-a9bb34f3efb6
ms.date: 04/23/2018
ms.keywords: BdaMethodDeletePin, BdaMethodDeletePin function [Streaming Media Devices], bdaref_6d81ac60-26e8-4cdb-ba9c-05f73cea187d.xml, bdasup/BdaMethodDeletePin, stream.bdamethoddeletepin
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
-	BdaMethodDeletePin
product:
- Windows
targetos: Windows
req.typenames: 
---

# BdaMethodDeletePin function


## -description


The <b>BdaMethodDeletePin</b> function deletes a pin factory.


## -parameters




### -param pIrp




### -param pKSMethod [in]

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a> structure that describes the method and request type of a method request.


### -param pvIgnored

Points to a buffer that is ignored.


#### - Irp [in]

Points to the IRP for the request to delete a pin factory. The BDA minidriver receives this IRP with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563415">KSMETHOD_BDA_DELETE_PIN_FACTORY</a> request.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaMethodDeletePin</b> function to delete a pin factory after the minidriver receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563415">KSMETHOD_BDA_DELETE_PIN_FACTORY</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a> method set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaMethodDeletePin</b> function directly, without intercepting this request using an internal method (<a href="https://msdn.microsoft.com/library/windows/hardware/ff567191">KStrMethodHandler</a>). See <a href="https://msdn.microsoft.com/1c0dace6-b618-4705-bf5d-65457d14c072">Defining Automation Tables</a> and <a href="https://msdn.microsoft.com/4af9efc3-8073-4111-9ad0-8b2fba4d1545">Configuring a BDA Filter</a> for more information. 

If a BDA minidriver must delete a pin without relying on the network provider, the BDA minidriver should call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556452">BdaDeletePin</a> function. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556452">BdaDeletePin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556467">BdaMethodCreatePin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563415">KSMETHOD_BDA_DELETE_PIN_FACTORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567191">KStrMethodHandler</a>
 

 

