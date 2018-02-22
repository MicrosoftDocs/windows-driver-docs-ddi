---
UID: NF:wdfdmaenabler.WdfDmaEnablerGetMaximumLength
title: WdfDmaEnablerGetMaximumLength function
author: windows-driver-content
description: The WdfDmaEnablerGetMaximumLength method returns the maximum transfer length, for a single DMA transfer, that a device supports.
old-location: wdf\wdfdmaenablergetmaximumlength.htm
old-project: wdf
ms.assetid: f37359b9-807e-43dc-a66b-7b32c0921f06
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfDmaEnablerGetMaximumLength method, wdf.wdfdmaenablergetmaximumlength, kmdf.wdfdmaenablergetmaximumlength, wdfdmaenabler/WdfDmaEnablerGetMaximumLength, WdfDmaEnablerGetMaximumLength, DFDmaObjectRef_8d6be540-2f98-48f9-8ffe-332c96394920.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDmaEnablerGetMaximumLength
product: Windows
targetos: Windows
req.typenames: WDF_DMA_PROFILE
req.product: Windows 10 or later.
---

# WdfDmaEnablerGetMaximumLength function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaEnablerGetMaximumLength</b> method returns the maximum transfer length, for a single <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transfer</a>, that a device supports. 


## -syntax


````
size_t WdfDmaEnablerGetMaximumLength(
  _In_ WDFDMAENABLER DmaEnabler
);
````


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object that the driver obtained from a previous call to <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>. 


## -returns



<b>WdfDmaEnablerGetMaximumLength</b> returns the maximum length of a DMA transfer, in bytes. This length is the same value that was specified in a previous call to <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>. 

A bug check occurs if the driver supplies an invalid object handle.






## -see-also

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>



<a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a>



<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablergetfragmentlength.md">WdfDmaEnablerGetFragmentLength</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaEnablerGetMaximumLength method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

