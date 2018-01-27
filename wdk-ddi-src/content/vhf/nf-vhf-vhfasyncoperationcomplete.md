---
UID: NF:vhf.VhfAsyncOperationComplete
title: VhfAsyncOperationComplete function
author: windows-driver-content
description: The HID source driver calls this method to set the results of an asynchronous operation.
old-location: hid\_vhfasyncoperationcomplete.htm
old-project: hid
ms.assetid: F28E6FC0-C2FE-4119-82D9-C38289340D3D
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: vhf/VhfAsyncOperationComplete, VhfAsyncOperationComplete method [Human Input Devices], VhfAsyncOperationComplete, hid._vhfasyncoperationcomplete
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
req.irql: <=DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	VhfKm.lib
-	VhfKm.dll
apiname: 
-	VhfAsyncOperationComplete
product: Windows
targetos: Windows
req.typenames: *PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
req.product: Windows 10 or later.
---

# VhfAsyncOperationComplete function


## -description


The HID source driver calls this method to set the results of an asynchronous operation. 


## -syntax


````
NTSTATUS VhfAsyncOperationComplete(
  [in] VHFOPERATIONHANDLE VhfOperationHandle,
  [in] NTSTATUS           CompletionStatus
);
````


## -parameters




### -param VhfOperationHandle [in]

The operation handle set by Virtual HID Framework (VHF). This handle is passed to the HID source driver  in the <i>VhfOperationHandle</i> parameter of <a href="..\vhf\nc-vhf-evt_vhf_async_operation.md">EvtVhfAsyncOperation</a>.


### -param CompletionStatus [in]

If the operation succeeds, the method returns STATUS_SUCCESS. Otherwise an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS </a> value.


## -returns


If the <b>VhfAsyncOperationComplete</b> call succeeds, the method returns STATUS_SUCCESS. Otherwise an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS </a> value.



## -remarks


The HID source driver can call  from the event callback or at a later time after returning from the <a href="..\vhf\nc-vhf-evt_vhf_async_operation.md">EvtVhfAsyncOperation</a> callback.



## -see-also

<a href="https://msdn.microsoft.com/26964963-792F-4529-B4FC-110BF5C65B35">Write a HID source driver by using Virtual HID Framework (VHF)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20VhfAsyncOperationComplete method%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

