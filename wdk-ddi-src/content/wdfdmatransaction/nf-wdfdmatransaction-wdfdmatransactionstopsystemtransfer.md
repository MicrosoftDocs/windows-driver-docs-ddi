---
UID: NF:wdfdmatransaction.WdfDmaTransactionStopSystemTransfer
title: WdfDmaTransactionStopSystemTransfer function
author: windows-driver-content
description: The WdfDmaTransactionStopSystemTransfer method attempts to stop a system-mode DMA transfer after the framework has called EvtProgramDma.
old-location: wdf\wdfdmatransactionstopsystemtransfer.htm
old-project: wdf
ms.assetid: 55674946-A2DA-4695-8673-6BF3123FB5FC
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfdmatransaction/WdfDmaTransactionStopSystemTransfer, WdfDmaTransactionStopSystemTransfer, wdf.wdfdmatransactionstopsystemtransfer, PFN_WDFDMATRANSACTIONSTOPSYSTEMTRANSFER, kmdf.wdfdmatransactionstopsystemtransfer, WdfDmaTransactionStopSystemTransfer method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: DriverCreate
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
-	WdfDmaTransactionStopSystemTransfer
product: Windows
targetos: Windows
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---

# WdfDmaTransactionStopSystemTransfer function


## -description


<p class="CCE_Message">[Applies to KMDF only]


   The 
  <b>WdfDmaTransactionStopSystemTransfer</b> method attempts to stop a system-mode DMA transfer after the framework has called <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a>.


## -syntax


````
void WdfDmaTransactionStopSystemTransfer(
  _In_ WDFDMATRANSACTION DmaTransaction
);
````


## -parameters




### -param DmaTransaction [in]

A handle to an initialized DMA transaction object.


## -returns


This method does not return a value.



## -remarks


Only a driver that uses system-mode DMA should call  <b>WdfDmaTransactionStopSystemTransfer</b>.

A driver using bus-mastering  DMA is responsible for programming its own dedicated DMA controller. In the event of a request cancellation, timeout, or device error, the driver can program the DMA controller to stop transferring data.

In contrast, a driver using system-mode DMA must rely on the hardware abstraction layer (HAL) to program the shared DMA controller.  When a driver calls <b>WdfDmaTransactionStopSystemTransfer</b>, the framework notifies the HAL that the transfer must be stopped and returns immediately.

The framework next calls the driver's <a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete.md">EvtDmaTransactionDmaTransferComplete</a> callback function, if the driver has provided one.  If not, the framework returns FALSE when the driver next calls <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompleted.md">WdfDmaTransactionDmaCompleted</a>.

If your driver calls this method on an operating system earlier than Windows 8, <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-kmdf-verifier">the framework's verifier</a> reports an error.

 For more information about system-mode DMA, see <a href="https://msdn.microsoft.com/CCC77C15-69CA-44CB-8DEB-29F3EAEA44F6">Supporting System-Mode DMA</a>.

 For more information about canceling DMA transactions, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-dma-transactions">Canceling DMA Transactions</a>.



## -see-also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncancel.md">WdfDmaTransactionCancel</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionStopSystemTransfer method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

