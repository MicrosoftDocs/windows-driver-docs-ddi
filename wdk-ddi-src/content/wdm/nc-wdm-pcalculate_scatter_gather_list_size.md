---
UID: NC:wdm.PCALCULATE_SCATTER_GATHER_LIST_SIZE
title: PCALCULATE_SCATTER_GATHER_LIST_SIZE
author: windows-driver-content
description: The CalculateScatterGatherList routine calculates the size, in bytes, of scatter/gather list necessary to hold a given buffer.
old-location: kernel\calculatescattergatherlist.htm
old-project: kernel
ms.assetid: d7509502-0965-44b9-8efb-cec4fbe3ac88
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: CalculateScatterGatherList, CalculateScatterGatherList callback function [Kernel-Mode Driver Architecture], PCALCULATE_SCATTER_GATHER_LIST_SIZE, kdma_f2e8ba68-4b5d-4a3c-9e81-1bf84cc7cc48.xml, kernel.calculatescattergatherlist, wdm/CalculateScatterGatherList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.lib: 
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wdm.h
apiname:
-	CalculateScatterGatherList
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PCALCULATE_SCATTER_GATHER_LIST_SIZE callback


## -description


The <b>CalculateScatterGatherList</b> routine calculates the size, in bytes, of scatter/gather list necessary to hold a given buffer.


## -prototype


````
PCALCULATE_SCATTER_GATHER_LIST_SIZE CalculateScatterGatherList;

NTSTATUS CalculateScatterGatherList(
  _In_      PDMA_ADAPTER DmaAdapter,
  _In_opt_  PMDL         Mdl,
  _In_      PVOID        CurrentVa,
  _In_      ULONG        Length,
  _Out_     PULONG       ScatterGatherListSize,
  _Out_opt_ PULONG       NumberOfMapRegisters
)
{ ... }
````


## -parameters




### -param DmaAdapter [in]

Pointer to the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure returned by <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.


### -param Mdl [in, optional]

Either <b>NULL</b> or a pointer to the MDL that contains the buffer. 


### -param CurrentVa [in]

Pointer to the virtual address of the beginning of the buffer. 


### -param Length [in]

Specifies the length of the buffer, in bytes. 


### -param ScatterGatherListSize [out]

Pointer to the variable the routine uses to return the size of the scatter/gather list, in bytes.


### -param pNumberOfMapRegisters








#### - NumberOfMapRegisters [out, optional]

Either <b>NULL</b> or pointer to the variable the routine uses to return the number of map registers needed for DMA operations on the buffer. 


## -returns



<b>CalculateScatterGatherList</b> returns one of the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The values returned in <i>ScatterGatherListSize</i> and <i>NumberOfMapRegisters</i> are valid. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The number of map registers required exceeds the number of map registers available. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>Length</i> is too big to fit within the buffer. 

</td>
</tr>
</table>
 




## -remarks



<b>CalculateScatterGatherList</b>
      is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a 
     <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
      structure. Drivers obtain the address of this routine by calling <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION2. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

If the caller passes <b>NULL</b> for the <i>Mdl</i> parameter, the routine calculates the maximum possible size needed to hold a scatter/gather list for the specified buffer. If the caller specifies the MDL that contains the buffer in the <i>Mdl</i> parameter, the routine computes the actual size needed to hold the scatter/gather list.

A driver uses <b>CalculateScatterGatherList</b> to allocate a scatter/gather list buffer to pass to <a href="..\wdm\nc-wdm-pbuild_scatter_gather_list.md">BuildScatterGatherList</a>.




## -see-also

<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>



<a href="..\wdm\nc-wdm-pbuild_scatter_gather_list.md">BuildScatterGatherList</a>



<a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>



<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>



<a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a>



<a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCALCULATE_SCATTER_GATHER_LIST_SIZE callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

