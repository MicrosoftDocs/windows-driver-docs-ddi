---
UID: NC:wdm.PPUT_DMA_ADAPTER
title: PPUT_DMA_ADAPTER
author: windows-driver-content
description: The PutDmaAdapter routine frees a DMA_ADAPTER structure previously allocated by IoGetDmaAdapter.
old-location: kernel\putdmaadapter.htm
tech.root: kernel
ms.assetid: 05a76baf-e5f7-41ca-ac9f-4538cd3e0292
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: PPUT_DMA_ADAPTER, PPUT_DMA_ADAPTER callback, PutDmaAdapter, PutDmaAdapter callback function [Kernel-Mode Driver Architecture], kdma_49fe7ec6-e0a3-445e-9275-08b94ca2cf48.xml, kernel.putdmaadapter, wdm/PutDmaAdapter
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wdm.h
api_name:
-	PutDmaAdapter
product:
- Windows
targetos: Windows
req.typenames: 
---

# PPUT_DMA_ADAPTER callback function


## -description


The <b>PutDmaAdapter</b> routine frees a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure previously allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.


## -parameters




### -param DmaAdapter [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure to be released.


## -returns



None




## -remarks



<b>PutDmaAdapter</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.

<b>PutDmaAdapter</b> frees a DMA adapter object previously allocated by <b>IoGetDmaAdapter</b>. Drivers should call <b>PutDmaAdapter</b> after completing DMA operations and freeing any map registers and common buffer allocated with this adapter object. After <b>PutDmaAdapter</b> returns, the driver can no longer use the DMA adapter object.

A driver must call <b>PutDmaAdapter</b> when it receives a PnP <a href="https://msdn.microsoft.com/library/windows/hardware/ff551755">IRP_MN_STOP_DEVICE</a> request. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>
 

 

