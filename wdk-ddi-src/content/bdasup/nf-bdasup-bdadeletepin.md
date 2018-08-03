---
UID: NF:bdasup.BdaDeletePin
title: BdaDeletePin function
author: windows-driver-content
description: The BdaDeletePin function deletes a pin from the specified filter.
old-location: stream\bdadeletepin.htm
tech.root: stream
ms.assetid: 32ff70d7-980c-4c80-8ebc-af2121bc64df
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: BdaDeletePin, BdaDeletePin function [Streaming Media Devices], bdaref_36a08eca-6cfb-4647-8252-05b6c8e0b8e1.xml, bdasup/BdaDeletePin, stream.bdadeletepin
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
-	BdaDeletePin
product:
- Windows
targetos: Windows
req.typenames: 
---

# BdaDeletePin function


## -description


The <b>BdaDeletePin</b> function deletes a pin from the specified filter. 


## -parameters




### -param pKSFilter [in]

Points to the filter in which to delete a pin.


### -param pulPinId [out, optional]

Points to a variable that contains the identifier for the pin to delete. 


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556474">BdaMethodDeletePin</a> function when the network provider dynamically deletes a pin using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563415">KSMETHOD_BDA_DELETE_PIN_FACTORY</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a> method set. If a BDA minidriver must delete a pin without relying on the network provider, the BDA minidriver should call the <b>BdaDeletePin</b> function directly.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556445">BdaCreatePin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556474">BdaMethodDeletePin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563415">KSMETHOD_BDA_DELETE_PIN_FACTORY</a>
 

 

