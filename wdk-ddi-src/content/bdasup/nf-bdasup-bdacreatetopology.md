---
UID: NF:bdasup.BdaCreateTopology
title: BdaCreateTopology function
author: windows-driver-content
description: The BdaCreateTopology function creates the topology between two pins.
old-location: stream\bdacreatetopology.htm
old-project: stream
ms.assetid: 855ef77c-2a85-4c8c-b8e3-c4aaa0d2a089
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: bdaref_bbf47d95-2b93-4e05-a5fa-aa5ed4968b0a.xml, stream.bdacreatetopology, bdasup/BdaCreateTopology, BdaCreateTopology function [Streaming Media Devices], BdaCreateTopology
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
-	BdaCreateTopology
product: Windows
targetos: Windows
req.typenames: KSP_BDA_NODE_PIN, *PKSP_BDA_NODE_PIN
---

# BdaCreateTopology function


## -description


The <b>BdaCreateTopology</b> function creates the topology between two pins. 


## -syntax


````
NTSTATUS BdaCreateTopology(
  _In_ PKSFILTER pKSFilter,
  _In_ ULONG     InputPinId,
  _In_ ULONG     OutputPinId
);
````


## -parameters




#### - pKSFilter [in]

Points to the BDA filter on which to create topology.


#### - InputPinId [in]

Specifies the identifier of the filter's input pin.


#### - OutputPinId [in]

Specifies the identifier of the filter's output pin.


## -returns


Returns STATUS_SUCCESS or an appropriate error code. Returns <b>NULL</b> if no valid pin pairing exists with the specified input and output pins. 





## -remarks


A BDA minidriver calls the <a href="..\bdasup\nf-bdasup-bdamethodcreatetopology.md">BdaMethodCreateTopology</a> function when the network provider dynamically creates a topology between filter pins using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563413">KSMETHOD_BDA_CREATE_TOPOLOGY</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a> method set. If a BDA minidriver must create a topology between filter pins without relying on the network provider, the BDA minidriver should call the <b>BdaCreateTopology</b> function directly.



## -see-also

<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563413">KSMETHOD_BDA_CREATE_TOPOLOGY</a>

<a href="..\bdasup\nf-bdasup-bdamethodcreatetopology.md">BdaMethodCreateTopology</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaCreateTopology function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

