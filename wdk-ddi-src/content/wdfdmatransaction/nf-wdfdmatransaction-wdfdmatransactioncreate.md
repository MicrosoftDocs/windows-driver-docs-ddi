---
UID: NF:wdfdmatransaction.WdfDmaTransactionCreate
title: WdfDmaTransactionCreate function
author: windows-driver-content
description: The WdfDmaTransactionCreate method creates a DMA transaction.
old-location: wdf\wdfdmatransactioncreate.htm
old-project: wdf
ms.assetid: 9470e4a6-eee4-4a73-80b0-3d45f9d79934
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDmaObjectRef_d7399240-2da3-418f-b21b-8a441e7923d4.xml, WdfDmaTransactionCreate, WdfDmaTransactionCreate method, kmdf.wdfdmatransactioncreate, wdf.wdfdmatransactioncreate, wdfdmatransaction/WdfDmaTransactionCreate
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDmaTransactionCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionCreate function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionCreate</b> method creates a DMA transaction.  


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object that the driver obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a>.  


### -param Attributes [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the new DMA transaction object. (The structure's <b>ParentObject</b> member must be <b>NULL</b>.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param DmaTransaction [out]

A handle to a DMA transaction object.


## -returns



<b>WdfDmaTransactionCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory to create a new DMA transaction object.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfDmaTransactionCreate</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.



This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



After your driver calls <b>WdfDmaTransactionCreate</b>, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547099">WdfDmaTransactionInitialize</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff547107">WdfDmaTransactionInitializeUsingRequest</a> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>. 

The specified DMA enabler object becomes the parent of the new DMA transaction object. The driver cannot change this parent, and the <b>ParentObject</b> member or the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure must be <b>NULL</b>.

For more information about DMA transactions, see <a href="https://msdn.microsoft.com/1982c3fa-9e4a-4b26-8902-321223d9159f">Creating and Initializing a DMA Transaction</a>. 


#### Examples

For a code example that uses <b>WdfDmaTransactionCreate</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547099">WdfDmaTransactionInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547107">WdfDmaTransactionInitializeUsingRequest</a>
 

 

