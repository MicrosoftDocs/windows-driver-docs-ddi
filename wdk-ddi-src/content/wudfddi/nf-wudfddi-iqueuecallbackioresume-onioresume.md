---
UID: NF:wudfddi.IQueueCallbackIoResume.OnIoResume
title: IQueueCallbackIoResume::OnIoResume method
author: windows-driver-content
description: The OnIoResume method resumes the processing of the specified I/O request from the specified queue.
old-location: wdf\iqueuecallbackioresume_onioresume.htm
old-project: wdf
ms.assetid: d34f6e2c-4227-41bb-a1c0-f6206daa700b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IQueueCallbackIoResume, IQueueCallbackIoResume interface, OnIoResume method, IQueueCallbackIoResume::OnIoResume, OnIoResume method, OnIoResume method, IQueueCallbackIoResume interface, OnIoResume,IQueueCallbackIoResume.OnIoResume, UMDFQueueObjectRef_fd16ca4e-eccf-49a2-a7f5-bce7e7931a77.xml, umdf.iqueuecallbackioresume_onioresume, wdf.iqueuecallbackioresume_onioresume, wudfddi/IQueueCallbackIoResume::OnIoResume
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IQueueCallbackIoResume.OnIoResume
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IQueueCallbackIoResume::OnIoResume method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnIoResume</b> method resumes the processing of the specified I/O request from the specified queue. 


## -parameters




### -param pWdfQueue [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a> interface for the I/O queue object that processing of the I/O request is resumed from. 


### -param pWdfRequest [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a> interface that represents the framework request object that is resumed. 


## -returns



None




## -remarks



A driver registers the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556862">IQueueCallbackIoResume</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556862">IQueueCallbackIoResume</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>
 

 

