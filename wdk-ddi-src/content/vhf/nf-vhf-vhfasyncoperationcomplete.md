---
UID: NF:vhf.VhfAsyncOperationComplete
title: VhfAsyncOperationComplete function (vhf.h)
description: The HID source driver calls this method to set the results of an asynchronous operation.
old-location: hid\_vhfasyncoperationcomplete.htm
tech.root: hid
ms.assetid: F28E6FC0-C2FE-4119-82D9-C38289340D3D
ms.date: 04/30/2018
keywords: ["VhfAsyncOperationComplete function"]
ms.keywords: VhfAsyncOperationComplete, VhfAsyncOperationComplete method [Human Input Devices], hid._vhfasyncoperationcomplete, vhf/VhfAsyncOperationComplete
f1_keywords:
 - "vhf/VhfAsyncOperationComplete"
 - "VhfAsyncOperationComplete"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- VhfKm.lib
- VhfKm.dll
api_name:
- VhfAsyncOperationComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# VhfAsyncOperationComplete function


## -description


The HID source driver calls this method to set the results of an asynchronous operation. 


## -parameters




### -param VhfOperationHandle [in]

The operation handle set by Virtual HID Framework (VHF). This handle is passed to the HID source driver  in the <i>VhfOperationHandle</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vhf/nc-vhf-evt_vhf_async_operation">EvtVhfAsyncOperation</a>.


### -param CompletionStatus [in]

If the operation succeeds, the method returns STATUS_SUCCESS. Otherwise an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS </a> value.


## -returns



If the <b>VhfAsyncOperationComplete</b> call succeeds, the method returns STATUS_SUCCESS. Otherwise an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS </a> value.




## -remarks



The HID source driver can call  from the event callback or at a later time after returning from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vhf/nc-vhf-evt_vhf_async_operation">EvtVhfAsyncOperation</a> callback.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/virtual-hid-framework--vhf-">Write a HID source driver by using Virtual HID Framework (VHF)</a>
 

 

