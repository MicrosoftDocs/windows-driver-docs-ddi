---
UID: NC:wdm.PFREE_COMMON_BUFFER
title: PFREE_COMMON_BUFFER
author: windows-driver-content
description: The FreeCommonBuffer routine frees a common buffer allocated by AllocateCommonBuffer, along with all resources the buffer uses.
old-location: kernel\freecommonbuffer.htm
old-project: kernel
ms.assetid: 9e026bde-657a-42ea-907c-71cc217dbd8d
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: FreeCommonBuffer, FreeCommonBuffer callback function [Kernel-Mode Driver Architecture], PFREE_COMMON_BUFFER, kdma_73f76fbd-2641-4002-90c8-ca412e969418.xml, kernel.freecommonbuffer, wdm/FreeCommonBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wdm.h
api_name:
-	FreeCommonBuffer
product:
- Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PFREE_COMMON_BUFFER callback


## -description


The <b>FreeCommonBuffer</b> routine frees a common buffer allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff540575">AllocateCommonBuffer</a>, along with all resources the buffer uses.


## -parameters




### -param DmaAdapter [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.


### -param Length [in]

Specifies the number of bytes to deallocate.


### -param LogicalAddress [in]

Specifies the logical address of the allocated memory range.


### -param VirtualAddress [in]

Pointer to the corresponding virtual address of the allocated memory range.


### -param CacheEnabled [in]

Indicates whether the allocated memory is cached.


## -returns



None




## -remarks



<b>FreeCommonBuffer</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.

To release a common buffer, a driver calls <b>FreeCommonBuffer</b> to unmap both its logical and virtual addresses. The parameters passed to <b>FreeCommonBuffer</b> must match exactly those passed to and returned from <a href="https://msdn.microsoft.com/library/windows/hardware/ff540575">AllocateCommonBuffer</a>. A driver cannot free part of an allocated common buffer. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540575">AllocateCommonBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>
 

 

