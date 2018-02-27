---
UID: NF:bdasup.BdaMethodCreatePin
title: BdaMethodCreatePin function
author: windows-driver-content
description: The BdaMethodCreatePin function creates a pin factory.
old-location: stream\bdamethodcreatepin.htm
old-project: stream
ms.assetid: 0bc31a97-661c-463d-a043-9f86f63bb4b4
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: BdaMethodCreatePin, BdaMethodCreatePin function [Streaming Media Devices], bdaref_492b1847-e4b7-4dfd-a8b1-c6c17fc6aff8.xml, bdasup/BdaMethodCreatePin, stream.bdamethodcreatepin
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
-	BdaMethodCreatePin
product: Windows
targetos: Windows
req.typenames: KSP_BDA_NODE_PIN, *PKSP_BDA_NODE_PIN
---

# BdaMethodCreatePin function


## -description


The <b>BdaMethodCreatePin</b> function creates a pin factory. 


## -syntax


````
NTSTATUS BdaMethodCreatePin(
  _In_      PIRP      Irp,
  _In_      PKSMETHOD pKSMethod,
  _Out_opt_ PULONG    pulPinFactoryID
);
````


## -parameters




### -param pIrp

TBD


### -param pKSMethod [in]

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a> structure that describes the method and request type of a method request.


### -param pulPinFactoryID [out, optional]

Points to a variable that receives the identifier of the pin factory. 


#### - Irp [in]

Points to the IRP for the request to create a pin factory. The BDA minidriver receives this IRP with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563411">KSMETHOD_BDA_CREATE_PIN_FACTORY</a> request.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaMethodCreatePin</b> function to create a pin factory after the minidriver receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563411">KSMETHOD_BDA_CREATE_PIN_FACTORY</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a> method set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaMethodCreatePin</b> function directly, without intercepting this request using an internal method (<a href="..\ks\nc-ks-pfnkshandler.md">KStrMethodHandler</a>). See <a href="https://msdn.microsoft.com/1c0dace6-b618-4705-bf5d-65457d14c072">Defining Automation Tables</a> and <a href="https://msdn.microsoft.com/4af9efc3-8073-4111-9ad0-8b2fba4d1545">Configuring a BDA Filter</a> for more information. 

If a BDA minidriver must create a pin without relying on the network provider, the BDA minidriver should call the <b>BdaCreatePin</b> function.




## -see-also

<a href="..\bdasup\nf-bdasup-bdacreatepin.md">BdaCreatePin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a>



<a href="..\bdasup\nf-bdasup-bdamethoddeletepin.md">BdaMethodDeletePin</a>



<a href="..\ks\nc-ks-pfnkshandler.md">KStrMethodHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563411">KSMETHOD_BDA_CREATE_PIN_FACTORY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaMethodCreatePin function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

