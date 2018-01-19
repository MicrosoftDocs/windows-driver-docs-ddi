---
UID: NF:bdasup.BdaMethodDeletePin
title: BdaMethodDeletePin function
author: windows-driver-content
description: The BdaMethodDeletePin function deletes a pin factory.
old-location: stream\bdamethoddeletepin.htm
old-project: stream
ms.assetid: 179419ee-2a99-4c03-9afb-a9bb34f3efb6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: BdaMethodDeletePin
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
req.alt-api: BdaMethodDeletePin
req.alt-loc: Bdasup.lib,Bdasup.dll
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
req.typenames: KSP_BDA_NODE_PIN, *PKSP_BDA_NODE_PIN
---

# BdaMethodDeletePin function



## -description
The <b>BdaMethodDeletePin</b> function deletes a pin factory.



## -syntax

````
NTSTATUS BdaMethodDeletePin(
  _In_ PIRP      Irp,
  _In_ PKSMETHOD pKSMethod,
       PVOID     pvIgnored
);
````


## -parameters

### -param Irp [in]

Points to the IRP for the request to delete a pin factory. The BDA minidriver receives this IRP with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563415">KSMETHOD_BDA_DELETE_PIN_FACTORY</a> request.


### -param pKSMethod [in]

Points to a <a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a> structure that describes the method and request type of a method request.


### -param pvIgnored 

Points to a buffer that is ignored.


## -returns
Returns STATUS_SUCCESS or an appropriate error code. 


## -remarks
A BDA minidriver calls the <b>BdaMethodDeletePin</b> function to delete a pin factory after the minidriver receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563415">KSMETHOD_BDA_DELETE_PIN_FACTORY</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a> method set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaMethodDeletePin</b> function directly, without intercepting this request using an internal method (<a href="..\ks\nc-ks-pfnkshandler.md">KStrMethodHandler</a>). See <a href="https://msdn.microsoft.com/1c0dace6-b618-4705-bf5d-65457d14c072">Defining Automation Tables</a> and <a href="https://msdn.microsoft.com/4af9efc3-8073-4111-9ad0-8b2fba4d1545">Configuring a BDA Filter</a> for more information. 

If a BDA minidriver must delete a pin without relying on the network provider, the BDA minidriver should call the <a href="..\bdasup\nf-bdasup-bdadeletepin.md">BdaDeletePin</a> function. 


## -see-also
<dl>
<dt>
<a href="..\bdasup\nf-bdasup-bdadeletepin.md">BdaDeletePin</a>
</dt>
<dt>
<a href="..\bdasup\nf-bdasup-bdamethodcreatepin.md">BdaMethodCreatePin</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563415">KSMETHOD_BDA_DELETE_PIN_FACTORY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a>
</dt>
<dt>
<a href="..\ks\nc-ks-pfnkshandler.md">KStrMethodHandler</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaMethodDeletePin function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

