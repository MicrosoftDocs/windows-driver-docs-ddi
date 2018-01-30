---
UID: NF:wdfdmatransaction.WdfDmaTransactionGetDevice
title: WdfDmaTransactionGetDevice function
author: windows-driver-content
description: The WdfDmaTransactionGetDevice method returns a handle to the framework device object that is associated with a specified DMA transaction.
old-location: wdf\wdfdmatransactiongetdevice.htm
old-project: wdf
ms.assetid: fa4d523b-4af2-4a6e-aaa6-d84c829b567d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDmaTransactionGetDevice, WdfDmaTransactionGetDevice method, kmdf.wdfdmatransactiongetdevice, wdf.wdfdmatransactiongetdevice, wdfdmatransaction/WdfDmaTransactionGetDevice, DFDmaObjectRef_eb3ef52a-cba0-4754-8dad-d113b200f949.xml, PFN_WDFDMATRANSACTIONGETDEVICE
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
-	WdfDmaTransactionGetDevice
product: Windows
targetos: Windows
req.typenames: "*PWDF_DMA_SYSTEM_PROFILE_CONFIG, WDF_DMA_SYSTEM_PROFILE_CONFIG"
req.product: Windows 10 or later.
---

# WdfDmaTransactionGetDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionGetDevice</b> method returns a handle to the framework device object that is associated with a specified DMA transaction.


## -syntax


````
WDFDEVICE WdfDmaTransactionGetDevice(
  _In_ WDFDMATRANSACTION DmaTransaction
);
````


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>. 


## -returns


<b>WdfDmaTransactionGetDevice</b> returns a handle to the framework device object that the driver specified when it called <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


For more information about completing DMA transfers, see <a href="https://msdn.microsoft.com/86383b9f-9b82-4afa-81ac-2ab09bd8778b">Completing a DMA Transfer</a>. 



## -see-also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionGetDevice method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

