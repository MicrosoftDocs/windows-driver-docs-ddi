---
UID: NF:wdfdmatransaction.WdfDmaTransactionGetRequest
title: WdfDmaTransactionGetRequest function
author: windows-driver-content
description: The WdfDmaTransactionGetRequest method retrieves a handle to the framework request object that is associated with a specified DMA transaction.
old-location: wdf\wdfdmatransactiongetrequest.htm
old-project: wdf
ms.assetid: 879bae2e-f608-4678-92ae-6100e59b6d52
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDmaTransactionGetRequest, kmdf.wdfdmatransactiongetrequest, PFN_WDFDMATRANSACTIONGETREQUEST, wdfdmatransaction/WdfDmaTransactionGetRequest, wdf.wdfdmatransactiongetrequest, DFDmaObjectRef_2564dedd-7db9-4c5d-905d-0939dc8cf24b.xml, WdfDmaTransactionGetRequest method
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDmaTransactionGetRequest
product: Windows
targetos: Windows
req.typenames: "*PWDF_DMA_SYSTEM_PROFILE_CONFIG, WDF_DMA_SYSTEM_PROFILE_CONFIG"
req.product: Windows 10 or later.
---

# WdfDmaTransactionGetRequest function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionGetRequest</b> method retrieves a handle to the framework request object that is associated with a specified DMA transaction.


## -syntax


````
WDFREQUEST WdfDmaTransactionGetRequest(
  _In_ WDFDMATRANSACTION DmaTransaction
);
````


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>.


## -returns



<b>WdfDmaTransactionGetRequest</b> returns a handle to the framework request object that is associated with the DMA transaction that the <i>DmaTransaction</i> parameter specified.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A driver can call <b>WdfDmaTransactionGetRequest</b> only for DMA transactions that the driver created by calling <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest.md">WdfDmaTransactionInitializeUsingRequest</a>. If a driver calls <b>WdfDmaTransactionGetRequest</b> for a DMA transaction that it created by calling <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitialize.md">WdfDmaTransactionInitialize</a>, <b>WdfDmaTransactionGetRequest</b> returns <b>NULL</b>.

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

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitialize.md">WdfDmaTransactionInitialize</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest.md">WdfDmaTransactionInitializeUsingRequest</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionGetRequest method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

