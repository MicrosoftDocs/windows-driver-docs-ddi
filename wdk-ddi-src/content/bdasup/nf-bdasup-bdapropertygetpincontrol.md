---
UID: NF:bdasup.BdaPropertyGetPinControl
title: BdaPropertyGetPinControl function
author: windows-driver-content
description: The BdaPropertyGetPinControl function retrieves either the identifier or type of a pin.
old-location: stream\bdapropertygetpincontrol.htm
old-project: stream
ms.assetid: ab240a95-6308-4953-95f6-9baa280ecf99
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: bdaref_f2db3de1-bfa0-4ad9-a537-6cc46f972984.xml, stream.bdapropertygetpincontrol, BdaPropertyGetPinControl, bdasup/BdaPropertyGetPinControl, BdaPropertyGetPinControl function [Streaming Media Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Bdasup.lib
-	Bdasup.dll
apiname:
-	BdaPropertyGetPinControl
product: Windows
targetos: Windows
req.typenames: KSP_BDA_NODE_PIN, *PKSP_BDA_NODE_PIN
---

# BdaPropertyGetPinControl function


## -description


The <b>BdaPropertyGetPinControl</b> function retrieves either the identifier or type of a pin. 


## -syntax


````
NTSTATUS BdaPropertyGetPinControl(
  _In_      PIRP        Irp,
  _In_      PKSPROPERTY pKSProperty,
  _Out_opt_ ULONG       *pulProperty
);
````


## -parameters




### -param Irp [in]

Points to the IRP for the request to retrieve pin information. The BDA minidriver receives this IRP with either the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564348">KSPROPERTY_BDA_PIN_ID</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff564350">KSPROPERTY_BDA_PIN_TYPE</a> request.


### -param Property

TBD


### -param pulProperty [out, optional]

Points to a variable that receives either the identifier or type of a pin. 


#### - pKSProperty [in]

Points to a <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property and request type of the property request.


## -returns


Returns STATUS_SUCCESS or an appropriate error code. 



## -remarks


A BDA minidriver calls the <b>BdaPropertyGetPinControl</b> function to retrieve either the identifier or type of a pin after the minidriver receives either a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564348">KSPROPERTY_BDA_PIN_ID</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff564350">KSPROPERTY_BDA_PIN_TYPE</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566552">KSPROPSETID_BdaPinControl</a> property set. Most BDA minidrivers can define pin-automation tables so that those minidrivers dispatch the <b>BdaPropertyGetPinControl</b> function directly, without intercepting this request using an internal get-handler (<a href="https://msdn.microsoft.com/library/windows/hardware/ff567177">KStrGetPropertyHandler</a>). 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564350">KSPROPERTY_BDA_PIN_TYPE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564348">KSPROPERTY_BDA_PIN_ID</a>

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566552">KSPROPSETID_BdaPinControl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaPropertyGetPinControl function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

