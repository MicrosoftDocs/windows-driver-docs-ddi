---
UID: NF:wdfdmaenabler.WdfDmaEnablerWdmGetDmaAdapter
title: WdfDmaEnablerWdmGetDmaAdapter function
author: windows-driver-content
description: The WdfDmaEnablerWdmGetDmaAdapter method returns a pointer to a WDM DMA_ADAPTER structure that is associated with a DMA enabler object.
old-location: wdf\wdfdmaenablerwdmgetdmaadapter.htm
old-project: wdf
ms.assetid: 2546303a-53c3-4c6b-a230-eb1ebd74cb76
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: kmdf.wdfdmaenablerwdmgetdmaadapter, WdfDmaEnablerWdmGetDmaAdapter method, DFDmaObjectRef_9ed5be1b-56fd-4305-8aad-0ebb0856e34a.xml, WdfDmaEnablerWdmGetDmaAdapter, wdf.wdfdmaenablerwdmgetdmaadapter, wdfdmaenabler/WdfDmaEnablerWdmGetDmaAdapter, PFN_WDFDMAENABLERWDMGETDMAADAPTER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.5
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
-	WdfDmaEnablerWdmGetDmaAdapter
product: Windows
targetos: Windows
req.typenames: WDF_DMA_PROFILE
req.product: Windows 10 or later.
---

# WdfDmaEnablerWdmGetDmaAdapter function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaEnablerWdmGetDmaAdapter</b> method returns a pointer to a WDM <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure that is associated with a DMA enabler object.


## -syntax


````
PDMA_ADAPTER WdfDmaEnablerWdmGetDmaAdapter(
  _In_ WDFDMAENABLER     DmaEnabler,
  _In_ WDF_DMA_DIRECTION DmaDirection
);
````


## -parameters




#### - DmaEnabler [in]

A handle to a DMA enabler object that the driver obtained from a previous call to <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>. 


#### - DmaDirection [in]

A <a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_direction.md">WDF_DMA_DIRECTION</a>-typed value that specifies the direction of the DMA transfer operation. For more information, see the following Remarks section.


## -returns


<b>WdfDmaEnablerWdmGetDmaAdapter</b> returns a pointer to a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure, or <b>NULL</b> if the <i>DmaDirection</i> parameter's value is invalid.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


When your driver calls <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>, the framework creates a separate <a href="https://msdn.microsoft.com/8bc672b4-0f4d-4e0c-9904-c8d0a3f3639c">adapter object</a> for each direction if the driver specifies a duplex profile, and it creates a single adapter object if the driver does not specify a duplex profile.

If your driver specified a duplex profile when it called <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>, the <b>WdfDmaEnablerWdmGetDmaAdapter</b> method's <i>DmaDirection</i> parameter's value must be <b>WdfDmaDirectionReadFromDevice</b> to obtain the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure for read operations and <b>WdfDmaDirectionWriteToDevice</b> to obtain the <b>DMA_ADAPTER</b> structure for write operations.  If your driver did not specify a duplex profile, the driver can specify either <b>WdfDmaDirectionReadFromDevice</b> or <b>WdfDmaDirectionWriteToDevice</b>.

The pointer that <b>WdfDmaEnablerWdmGetDmaAdapter</b> returns is valid until the DMA enabler object is deleted. If the driver provides an <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> function for the DMA enabler object, the pointer is valid until the callback function returns.



## -see-also

<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>

<a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_direction.md">WDF_DMA_DIRECTION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaEnablerWdmGetDmaAdapter method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

