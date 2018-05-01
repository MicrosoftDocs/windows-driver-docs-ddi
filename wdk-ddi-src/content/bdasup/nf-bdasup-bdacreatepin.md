---
UID: NF:bdasup.BdaCreatePin
title: BdaCreatePin function
author: windows-driver-content
description: The BdaCreatePin function creates a new pin in the specified filter.
old-location: stream\bdacreatepin.htm
old-project: stream
ms.assetid: ac69fdaa-f1e3-4487-93e1-f900f73be2fe
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: BdaCreatePin, BdaCreatePin function [Streaming Media Devices], bdaref_e84fba91-044c-40f3-9364-ede0bbabda48.xml, bdasup/BdaCreatePin, stream.bdacreatepin
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
-	BdaCreatePin
product: Windows
targetos: Windows
req.typenames: 
---

# BdaCreatePin function


## -description


The <b>BdaCreatePin</b> function creates a new pin in the specified filter. 


## -parameters




### -param pKSFilter [in]

Points to the filter in which to create a pin.


### -param ulPinType [in]

Specifies the type of pin to create. The BDA minidriver must define a list of pin types for each filter that it supports.


### -param pulPinId [out, optional]

Points to a variable that receives the identifier for the created pin. 


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556467">BdaMethodCreatePin</a> function when the network provider dynamically creates a pin using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563411">KSMETHOD_BDA_CREATE_PIN_FACTORY</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a> method set. If a BDA minidriver must create a pin without relying on the network provider, the BDA minidriver should call the <b>BdaCreatePin</b> function directly.

.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556452">BdaDeletePin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556467">BdaMethodCreatePin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563411">KSMETHOD_BDA_CREATE_PIN_FACTORY</a>
 

 

