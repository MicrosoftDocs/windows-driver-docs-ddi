---
UID: NF:wdfdmaenabler.WdfDmaEnablerGetFragmentLength
title: WdfDmaEnablerGetFragmentLength function
author: windows-driver-content
description: The WdfDmaEnablerGetFragmentLength method returns the maximum transfer length that the operating system supports for a single DMA transfer.
old-location: wdf\wdfdmaenablergetfragmentlength.htm
old-project: wdf
ms.assetid: f7481655-4413-4937-8a0a-99ca07d5b7b0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDmaEnablerGetFragmentLength method, kmdf.wdfdmaenablergetfragmentlength, wdfdmaenabler/WdfDmaEnablerGetFragmentLength, PFN_WDFDMAENABLERGETFRAGMENTLENGTH, DFDmaObjectRef_7c147fef-46f6-49aa-b8a9-9ef1a82ef963.xml, WdfDmaEnablerGetFragmentLength, wdf.wdfdmaenablergetfragmentlength
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.1
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
-	WdfDmaEnablerGetFragmentLength
product: Windows
targetos: Windows
req.typenames: WDF_DMA_PROFILE
req.product: Windows 10 or later.
---

# WdfDmaEnablerGetFragmentLength function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaEnablerGetFragmentLength</b> method returns the maximum transfer length that the operating system supports for a single <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transfer</a>.


## -syntax


````
size_t WdfDmaEnablerGetFragmentLength(
  _In_ WDFDMAENABLER     DmaEnabler,
  _In_ WDF_DMA_DIRECTION DmaDirection
);
````


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object that the driver obtained from a previous call to <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>. 


### -param DmaDirection [in]

A <a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_direction.md">WDF_DMA_DIRECTION</a>-typed value that specifies the direction of the DMA transfer operation. For more information, see the following Remarks section.


## -returns


<b>WdfDmaEnablerGetFragmentLength</b> returns the maximum length of a DMA transfer, in bytes, that the operating system can support, or zero if the <i>DmaDirection</i> parameter's value is invalid.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


The maximum DMA transfer length that the operating system can support depends on the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff554406">map registers</a> that are available. If enough map registers are available, <b>WdfDmaEnablerGetFragmentLength</b> returns the same value that <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablergetmaximumlength.md">WdfDmaEnablerGetMaximumLength</a> returns. Otherwise, the value that <b>WdfDmaEnablerGetFragmentLength</b> returns will be less than the value that <b>WdfDmaEnablerGetMaximumLength</b> returns.

Your driver can determine the number of map registers that are available by using the BYTE_TO_PAGES macro, as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BYTE_TO_PAGES(WdfDmaEnablerGetFragmentLength()) + 1</pre>
</td>
</tr>
</table></span></div>If your driver specified a duplex profile when it called <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>, the <i>DmaDirection</i> parameter's value must be <b>WdfDmaDirectionReadFromDevice</b> to obtain the maximum transfer length for read operations and <b>WdfDmaDirectionWriteToDevice</b> to obtain the maximum transfer length for write operations. If your driver did not specify a duplex profile, the driver can specify either <b>WdfDmaDirectionReadFromDevice</b> or <b>WdfDmaDirectionWriteToDevice</b> for <i>DmaDirection</i>.

Note that if your driver's device supports duplex operation, <b>WdfDmaEnablerGetFragmentLength</b> can return different values for the read and write directions that the <i>DmaDirection</i> parameter specifies. This difference is because the framework creates a separate <a href="https://msdn.microsoft.com/8bc672b4-0f4d-4e0c-9904-c8d0a3f3639c">adapter object</a> for each direction, and the operating system might provide a different number of map registers to each adapter object.



## -see-also

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablergetmaximumlength.md">WdfDmaEnablerGetMaximumLength</a>

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>

<a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_direction.md">WDF_DMA_DIRECTION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaEnablerGetFragmentLength method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

