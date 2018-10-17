---
UID: NC:wdm.PGET_DMA_ALIGNMENT
title: PGET_DMA_ALIGNMENT
author: windows-driver-content
description: The GetDmaAlignment routine returns the alignment requirements of the DMA system.
old-location: kernel\getdmaalignment.htm
tech.root: kernel
ms.assetid: c96ed5ad-34d8-4530-8d00-483e5aee7261
ms.date: 4/30/2018
ms.keywords: GetDmaAlignment, GetDmaAlignment callback function [Kernel-Mode Driver Architecture], PGET_DMA_ALIGNMENT, PGET_DMA_ALIGNMENT callback, kdma_3b830c2d-6c3d-477c-b781-c9d1a7dbe5bf.xml, kernel.getdmaalignment, wdm/GetDmaAlignment
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with  Windows 2000.
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
-	Wdm.h
api_name:
-	GetDmaAlignment
product:
- Windows
targetos: Windows
req.typenames: 
---

# PGET_DMA_ALIGNMENT callback function


## -description


The <b>GetDmaAlignment</b> routine returns the alignment requirements of the DMA system.


## -parameters




### -param DmaAdapter [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller. 


## -returns



<b>GetDmaAlignment</b> returns the alignment requirements, in bytes, of the DMA system.  The starting address and length of DMA buffers must be a multiple of this value.




## -remarks



<b>GetDmaAlignment</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.

A driver can call this routine to determine alignment requirements for DMA buffers it allocates. The returned value should be used to set the <b>AlignmentRequirement</b> field in the device object. A driver may need to increase this value because of additional hardware device restrictions.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547807">Initializing a Device Object</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>
 

 

