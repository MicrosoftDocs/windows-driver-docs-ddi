---
UID: NF:wdfdmaenabler.WDF_DMA_ENABLER_CONFIG_INIT
title: WDF_DMA_ENABLER_CONFIG_INIT function
author: windows-driver-content
description: The WDF_DMA_ENABLER_CONFIG_INIT function initializes a driver's WDF_DMA_ENABLER_CONFIG structure.
old-location: wdf\wdf_dma_enabler_config_init.htm
old-project: wdf
ms.assetid: b01efb50-a3b2-4ffd-83e6-daa0ebbc6484
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfdmaenabler/WDF_DMA_ENABLER_CONFIG_INIT, WDF_DMA_ENABLER_CONFIG_INIT, kmdf.wdf_dma_enabler_config_init, WDF_DMA_ENABLER_CONFIG_INIT function, DFDmaObjectRef_2d577e59-2038-4850-a67c-6e7f3b795387.xml, wdf.wdf_dma_enabler_config_init
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdmaenabler.h
apiname:
-	WDF_DMA_ENABLER_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: WDF_DMA_PROFILE
req.product: Windows 10 or later.
---

# WDF_DMA_ENABLER_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_DMA_ENABLER_CONFIG_INIT</b> function initializes a driver's <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a> structure.


## -syntax


````
VOID WDF_DMA_ENABLER_CONFIG_INIT(
  _Out_ PWDF_DMA_ENABLER_CONFIG Config,
  _In_  WDF_DMA_PROFILE         Profile,
  _In_  size_t                  MaximumLength
);
````


## -parameters




### -param Config [out]

A pointer to a driver-allocated <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a> structure.


### -param Profile [in]

A value for the <b>Profile</b> member of the <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a> structure.


### -param MaximumLength [in]

A value for the <b>MaximumLength</b> member of the <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a> structure.


## -returns



None




## -remarks



Drivers must call the <b>WDF_DMA_ENABLER_CONFIG_INIT</b> function before calling <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>. 


#### Examples

For a code example that uses <b>WDF_DMA_ENABLER_CONFIG_INIT</b>, see <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>.

<div class="code"></div>



## -see-also

<a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a>



<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DMA_ENABLER_CONFIG_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

