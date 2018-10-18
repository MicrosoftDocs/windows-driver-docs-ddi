---
UID: NF:wdfdmatransaction.WdfDmaTransactionGetRequest
title: WdfDmaTransactionGetRequest function
author: windows-driver-content
description: The WdfDmaTransactionGetRequest method retrieves a handle to the framework request object that is associated with a specified DMA transaction.
old-location: wdf\wdfdmatransactiongetrequest.htm
tech.root: wdf
ms.assetid: 879bae2e-f608-4678-92ae-6100e59b6d52
ms.date: 2/26/2018
ms.keywords: DFDmaObjectRef_2564dedd-7db9-4c5d-905d-0939dc8cf24b.xml, WdfDmaTransactionGetRequest, WdfDmaTransactionGetRequest method, kmdf.wdfdmatransactiongetrequest, wdf.wdfdmatransactiongetrequest, wdfdmatransaction/WdfDmaTransactionGetRequest
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDmaTransactionGetRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionGetRequest function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaTransactionGetRequest</b> method retrieves a handle to the framework request object that is associated with a specified DMA transaction.


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>.


## -returns



<b>WdfDmaTransactionGetRequest</b> returns a handle to the framework request object that is associated with the DMA transaction that the <i>DmaTransaction</i> parameter specified.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A driver can call <b>WdfDmaTransactionGetRequest</b> only for DMA transactions that the driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547107">WdfDmaTransactionInitializeUsingRequest</a>. If a driver calls <b>WdfDmaTransactionGetRequest</b> for a DMA transaction that it created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547099">WdfDmaTransactionInitialize</a>, <b>WdfDmaTransactionGetRequest</b> returns <b>NULL</b>.

For more information about completing DMA transfers, see <a href="https://msdn.microsoft.com/86383b9f-9b82-4afa-81ac-2ab09bd8778b">Completing a DMA Transfer</a>. 


#### Examples

The following code example obtains a handle to the framework request object that is associated with a specified DMA transaction.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFREQUEST  request;

request = WdfDmaTransactionGetRequest(dmaTransaction);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547099">WdfDmaTransactionInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547107">WdfDmaTransactionInitializeUsingRequest</a>
 

 

