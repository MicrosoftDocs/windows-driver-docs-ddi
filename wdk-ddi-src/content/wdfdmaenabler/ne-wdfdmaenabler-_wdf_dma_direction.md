---
UID: NE:wdfdmaenabler._WDF_DMA_DIRECTION
title: "_WDF_DMA_DIRECTION"
author: windows-driver-content
description: The WDF_DMA_DIRECTION enumeration defines the direction of a DMA transfer.
old-location: wdf\wdf_dma_direction.htm
old-project: wdf
ms.assetid: 813414fa-17b6-4b69-a3dd-f3a2e5190305
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WDF_DMA_DIRECTION enumeration, wdf.wdf_dma_direction, WdfDmaDirectionReadFromDevice, WdfDmaDirectionWriteToDevice, _WDF_DMA_DIRECTION, wdfdmaenabler/WdfDmaDirectionWriteToDevice, WDF_DMA_DIRECTION, DFDmaObjectRef_e790f51f-b8cb-4e04-a5f3-49f24fabf5b8.xml, wdfdmaenabler/WDF_DMA_DIRECTION, wdfdmaenabler/WdfDmaDirectionReadFromDevice, kmdf.wdf_dma_direction
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Windows
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
req.lib: 
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
-	WDF_DMA_DIRECTION
product: Windows
targetos: Windows
req.typenames: WDF_DMA_DIRECTION
req.product: Windows 10 or later.
---

# _WDF_DMA_DIRECTION enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_DMA_DIRECTION</b> enumeration defines the direction of a DMA transfer.


## -syntax


````
typedef enum _WDF_DMA_DIRECTION { 
  WdfDmaDirectionReadFromDevice  = FALSE,
  WdfDmaDirectionWriteToDevice   = TRUE
} WDF_DMA_DIRECTION;
````


## -enum-fields




### -field WdfDmaDirectionReadFromDevice

The DMA transfer direction is from the device (read).


### -field WdfDmaDirectionWriteToDevice

The DMA transfer direction is to the device (write).


## -remarks



The <b>WDF_DMA_DIRECTION</b> enumeration is used as input to the <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> callback function and the <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitialize.md">WdfDmaTransactionInitialize</a> and <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest.md">WdfDmaTransactionInitializeUsingRequest</a> methods.




## -see-also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest.md">WdfDmaTransactionInitializeUsingRequest</a>



<a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest.md">WdfDmaTransactionInitializeUsingRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DMA_DIRECTION enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

