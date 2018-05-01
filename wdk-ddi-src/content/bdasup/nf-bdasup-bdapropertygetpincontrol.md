---
UID: NF:bdasup.BdaPropertyGetPinControl
title: BdaPropertyGetPinControl function
author: windows-driver-content
description: The BdaPropertyGetPinControl function retrieves either the identifier or type of a pin.
old-location: stream\bdapropertygetpincontrol.htm
old-project: stream
ms.assetid: ab240a95-6308-4953-95f6-9baa280ecf99
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: BdaPropertyGetPinControl, BdaPropertyGetPinControl function [Streaming Media Devices], bdaref_f2db3de1-bfa0-4ad9-a537-6cc46f972984.xml, bdasup/BdaPropertyGetPinControl, stream.bdapropertygetpincontrol
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
-	BdaPropertyGetPinControl
product: Windows
targetos: Windows
req.typenames: 
---

# BdaPropertyGetPinControl function


## -description


The <b>BdaPropertyGetPinControl</b> function retrieves either the identifier or type of a pin. 


## -parameters




### -param Irp [in]

Points to the IRP for the request to retrieve pin information. The BDA minidriver receives this IRP with either the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564348">KSPROPERTY_BDA_PIN_ID</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff564350">KSPROPERTY_BDA_PIN_TYPE</a> request.


### -param Property

TBD


### -param pulProperty [out, optional]

Points to a variable that receives either the identifier or type of a pin. 


#### - pKSProperty [in]

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property and request type of the property request.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaPropertyGetPinControl</b> function to retrieve either the identifier or type of a pin after the minidriver receives either a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564348">KSPROPERTY_BDA_PIN_ID</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff564350">KSPROPERTY_BDA_PIN_TYPE</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566552">KSPROPSETID_BdaPinControl</a> property set. Most BDA minidrivers can define pin-automation tables so that those minidrivers dispatch the <b>BdaPropertyGetPinControl</b> function directly, without intercepting this request using an internal get-handler (<a href="https://msdn.microsoft.com/library/windows/hardware/ff567177">KStrGetPropertyHandler</a>). 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564348">KSPROPERTY_BDA_PIN_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564350">KSPROPERTY_BDA_PIN_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566552">KSPROPSETID_BdaPinControl</a>
 

 

