---
UID: NF:wdfdmaenabler.WdfDmaEnablerGetMaximumScatterGatherElements
title: WdfDmaEnablerGetMaximumScatterGatherElements function
author: windows-driver-content
description: The WdfDmaEnablerGetMaximumScatterGatherElements method returns the maximum number of scatter/gather elements that the device and driver support, for a specified DMA enabler object.
old-location: wdf\wdfdmaenablergetmaximumscattergatherelements.htm
old-project: wdf
ms.assetid: de02d40d-3438-4a34-9e2b-07a7d9c4c8ac
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFDMAENABLERGETMAXIMUMSCATTERGATHERELEMENTS, DFDmaObjectRef_34ec0aef-b846-4b23-b9b3-01e8834821f7.xml, wdfdmaenabler/WdfDmaEnablerGetMaximumScatterGatherElements, kmdf.wdfdmaenablergetmaximumscattergatherelements, wdf.wdfdmaenablergetmaximumscattergatherelements, WdfDmaEnablerGetMaximumScatterGatherElements, WdfDmaEnablerGetMaximumScatterGatherElements method
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
-	WdfDmaEnablerGetMaximumScatterGatherElements
product: Windows
targetos: Windows
req.typenames: WDF_DMA_PROFILE
req.product: Windows 10 or later.
---

# WdfDmaEnablerGetMaximumScatterGatherElements function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaEnablerGetMaximumScatterGatherElements</b> method returns the maximum number of scatter/gather elements that the device and driver support, for a specified DMA enabler object. 


## -syntax


````
size_t WdfDmaEnablerGetMaximumScatterGatherElements(
  _In_ WDFDMAENABLER DmaEnabler
);
````


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object that the driver obtained from a previous call to <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>. 


## -returns


If the driver previously called <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablersetmaximumscattergatherelements.md">WdfDmaEnablerSetMaximumScatterGatherElements</a>, <b>WdfDmaEnablerGetMaximumScatterGatherElements</b> returns the value that the driver specified in the previous call. Otherwise, <b>WdfDmaEnablerGetMaximumScatterGatherElements</b> returns WDF_DMA_ENABLER_UNLIMITED_FRAGMENTS, which indicates that there is no limit to the number of scatter/gather elements.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


For more information about this method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enabling-dma-transactions">Enabling DMA Transactions</a>.



## -see-also

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablersetmaximumscattergatherelements.md">WdfDmaEnablerSetMaximumScatterGatherElements</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaEnablerGetMaximumScatterGatherElements method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

