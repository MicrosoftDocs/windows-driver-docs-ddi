---
UID: NF:wdfdmatransaction.WdfDmaTransactionGetDevice
title: WdfDmaTransactionGetDevice function
author: windows-driver-content
description: The WdfDmaTransactionGetDevice method returns a handle to the framework device object that is associated with a specified DMA transaction.
old-location: wdf\wdfdmatransactiongetdevice.htm
tech.root: wdf
ms.assetid: fa4d523b-4af2-4a6e-aaa6-d84c829b567d
ms.date: 02/26/2018
ms.keywords: DFDmaObjectRef_eb3ef52a-cba0-4754-8dad-d113b200f949.xml, WdfDmaTransactionGetDevice, WdfDmaTransactionGetDevice method, kmdf.wdfdmatransactiongetdevice, wdf.wdfdmatransactiongetdevice, wdfdmatransaction/WdfDmaTransactionGetDevice
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
-	WdfDmaTransactionGetDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionGetDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaTransactionGetDevice</b> method returns a handle to the framework device object that is associated with a specified DMA transaction.


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>. 


## -returns



<b>WdfDmaTransactionGetDevice</b> returns a handle to the framework device object that the driver specified when it called <a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about completing DMA transfers, see <a href="https://msdn.microsoft.com/86383b9f-9b82-4afa-81ac-2ab09bd8778b">Completing a DMA Transfer</a>. 


#### Examples

The following code example obtains a handle to the framework device object that is associated with a specified DMA transaction.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFDEVICE device;

device = WdfDmaTransactionGetDevice(DmaTransaction);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>
 

 

