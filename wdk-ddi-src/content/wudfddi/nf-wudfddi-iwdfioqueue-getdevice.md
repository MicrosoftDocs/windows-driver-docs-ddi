---
UID: NF:wudfddi.IWDFIoQueue.GetDevice
title: IWDFIoQueue::GetDevice method
author: windows-driver-content
description: The GetDevice method retrieves the interface to the device that owns the I/O queue.
old-location: wdf\iwdfioqueue_getdevice.htm
old-project: wdf
ms.assetid: e1c1a67e-a18d-4eef-88ce-cd7edd371f54
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetDevice method, GetDevice method, IWDFIoQueue interface, GetDevice,IWDFIoQueue.GetDevice, IWDFIoQueue, IWDFIoQueue interface, GetDevice method, IWDFIoQueue::GetDevice, UMDFQueueObjectRef_ecef922c-aff2-49ac-84bd-17e7e2e784a1.xml, umdf.iwdfioqueue_getdevice, wdf.iwdfioqueue_getdevice, wudfddi/IWDFIoQueue::GetDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoQueue.GetDevice
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoQueue::GetDevice method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDevice</b> method retrieves the interface to the device that owns the I/O queue.


## -syntax


````
void GetDevice(
  [out] IWDFDevice **ppWdfDevice
);
````


## -parameters




### -param ppWdfDevice [out]

A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a> interface for the device object, if the call succeeds; otherwise, this parameter is <b>NULL</b>.


## -returns



None




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>



 

 


