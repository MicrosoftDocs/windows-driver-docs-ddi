---
UID: NS:wdm._SCATTER_GATHER_LIST
title: "_SCATTER_GATHER_LIST"
author: windows-driver-content
description: The SCATTER_GATHER_LIST structure describes the scatter/gather list for a DMA operation.
old-location: kernel\scatter_gather_list.htm
tech.root: kernel
ms.assetid: 3cc6da15-8367-4430-afe8-956376eef1c7
ms.date: 04/30/2018
ms.keywords: "*PSCATTER_GATHER_LIST, PSCATTER_GATHER_LIST, PSCATTER_GATHER_LIST structure pointer [Kernel-Mode Driver Architecture], SCATTER_GATHER_LIST, SCATTER_GATHER_LIST structure [Kernel-Mode Driver Architecture], _SCATTER_GATHER_LIST, kernel.scatter_gather_list, kstruct_d_b8c13069-6d90-4fcf-8582-c57bf11509ea.xml, wdm/PSCATTER_GATHER_LIST, wdm/SCATTER_GATHER_LIST"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	SCATTER_GATHER_LIST
product:
- Windows
targetos: Windows
req.typenames: SCATTER_GATHER_LIST, *PSCATTER_GATHER_LIST
---

# _SCATTER_GATHER_LIST structure


## -description


The <b>SCATTER_GATHER_LIST</b> structure describes the scatter/gather list for a DMA operation.


## -struct-fields




### -field NumberOfElements

Specifies the number of elements in the <b>Elements</b> array.


### -field Reserved

Reserved for future use.


### -field Elements

Specifies an array of scatter/gather elements that comprise a scatter/gather list. Each array element is a structure of type <b>SCATTER_GATHER_ELEMENT</b>, which is defined as follows:

<pre class="syntax" xml:space="preserve"><code>typedef struct _SCATTER_GATHER_ELEMENT {
  PHYSICAL_ADDRESS  Address;
  ULONG  Length;
  ULONG_PTR  Reserved;
} SCATTER_GATHER_ELEMENT, *PSCATTER_GATHER_ELEMENT;</code></pre>
The <b>SCATTER_GATHER_ELEMENT</b> structure specifies the length, in bytes, of a physically contiguous scatter/gather region and the starting physical address of this region.


## -remarks



For a driver that performs scatter/gather DMA, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546531">GetScatterGatherList</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff540689">BuildScatterGatherList</a> routine creates a scatter/gather list and passes this list to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540513">AdapterListControl</a> routine. This scatter/gather list consists of a <b>SCATTER_GATHER_LIST</b> structure that is immediately followed in memory by a <b>SCATTER_GATHER_ELEMENT</b> array. The number of elements in this array is specified by the <b>NumberOfElements</b> member of the <b>SCATTER_GATHER_LIST</b> structure.

For more information about scatter/gather lists, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565510">Using Scatter/Gather DMA</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540513">AdapterListControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540689">BuildScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546531">GetScatterGatherList</a>
 

 

