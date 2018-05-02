---
UID: NF:vhf.VhfAsyncOperationComplete
title: VhfAsyncOperationComplete function
author: windows-driver-content
description: The HID source driver calls this method to set the results of an asynchronous operation.
old-location: hid\_vhfasyncoperationcomplete.htm
old-project: hid
ms.assetid: F28E6FC0-C2FE-4119-82D9-C38289340D3D
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: VhfAsyncOperationComplete, VhfAsyncOperationComplete method [Human Input Devices], hid._vhfasyncoperationcomplete, vhf/VhfAsyncOperationComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vhf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: VhfKm.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	VhfKm.lib
-	VhfKm.dll
api_name:
-	VhfAsyncOperationComplete
product: Windows
targetos: Windows
req.typenames: 
---

# VhfAsyncOperationComplete function


## -description


The HID source driver calls this method to set the results of an asynchronous operation. 


## -parameters




### -param VhfOperationHandle [in]

The operation handle set by Virtual HID Framework (VHF). This handle is passed to the HID source driver  in the <i>VhfOperationHandle</i> parameter of <a href="https://msdn.microsoft.com/C42174FE-202F-405D-840B-8613762F43AC">EvtVhfAsyncOperation</a>.


### -param CompletionStatus [in]

If the operation succeeds, the method returns STATUS_SUCCESS. Otherwise an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS </a> value.


## -returns



If the <b>VhfAsyncOperationComplete</b> call succeeds, the method returns STATUS_SUCCESS. Otherwise an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS </a> value.




## -remarks



The HID source driver can call  from the event callback or at a later time after returning from the <a href="https://msdn.microsoft.com/C42174FE-202F-405D-840B-8613762F43AC">EvtVhfAsyncOperation</a> callback.




## -see-also




<a href="https://msdn.microsoft.com/26964963-792F-4529-B4FC-110BF5C65B35">Write a HID source driver by using Virtual HID Framework (VHF)</a>
 

 

