---
UID: NF:bdasup.BdaValidateNodeProperty
title: BdaValidateNodeProperty function
author: windows-driver-content
description: The BdaValidateNodeProperty function validates that a node property request is associated with a specific pin.
old-location: stream\bdavalidatenodeproperty.htm
tech.root: stream
ms.assetid: e3a6d757-68c5-49d1-92cc-0ebf6ba6bbec
ms.date: 4/23/2018
ms.keywords: BdaValidateNodeProperty, BdaValidateNodeProperty function [Streaming Media Devices], bdaref_a6f1ec2f-9e23-4cbb-a3dc-fab0d2c5ca1c.xml, bdasup/BdaValidateNodeProperty, stream.bdavalidatenodeproperty
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
-	BdaValidateNodeProperty
product:
- Windows
targetos: Windows
req.typenames: 
---

# BdaValidateNodeProperty function


## -description


The <b>BdaValidateNodeProperty</b> function validates that a node property request is associated with a specific pin. 


## -parameters




### -param pIrp




### -param pProperty






#### - Irp [in]

Points to the IRP for the request to validate that the current pin controls the node property at <i>pKSProperty</i>. The BDA minidriver can receive this IRP with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564355">KSPROPERTY_BDA_RF_TUNER_FREQUENCY</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff564286">KSPROPERTY_BDA_AUTODEMODULATE_START</a> request.


#### - pKSProperty [in]

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property and request type of the property request.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A pin method in a BDA minidriver calls the <b>BdaValidateNodeProperty</b> function to validate that the pin controls a specific node property after the minidriver receives the node property request from the network provider. This node property request can be, for example, a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564355">KSPROPERTY_BDA_RF_TUNER_FREQUENCY</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566542">KSPROPSETID_BdaFrequencyFilter</a> property set or a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564286">KSPROPERTY_BDA_AUTODEMODULATE_START</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566533">KSPROPSETID_BdaAutodemodulate</a> property set. These property sets manipulate tuner and demodulator nodes. After successfully calling <b>BdaValidateNodeProperty</b>, the minidriver obtains a pointer to the BDA filter from the passed IRP so that the minidriver can perform an operation on the particular node. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564286">KSPROPERTY_BDA_AUTODEMODULATE_START</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564355">KSPROPERTY_BDA_RF_TUNER_FREQUENCY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566533">KSPROPSETID_BdaAutodemodulate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566542">KSPROPSETID_BdaFrequencyFilter</a>
 

 

