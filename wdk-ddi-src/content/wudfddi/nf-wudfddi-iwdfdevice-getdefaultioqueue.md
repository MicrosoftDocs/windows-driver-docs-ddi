---
UID: NF:wudfddi.IWDFDevice.GetDefaultIoQueue
title: IWDFDevice::GetDefaultIoQueue (wudfddi.h)
description: The GetDefaultIoQueue method retrieves the interface of the default I/O queue for a device.
old-location: wdf\iwdfdevice_getdefaultioqueue.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFDevice::GetDefaultIoQueue"]
ms.keywords: GetDefaultIoQueue, GetDefaultIoQueue method, GetDefaultIoQueue method,IWDFDevice interface, IWDFDevice interface,GetDefaultIoQueue method, IWDFDevice.GetDefaultIoQueue, IWDFDevice::GetDefaultIoQueue, UMDFDeviceObjectRef_b4c10b3b-eba4-4e6c-8f9e-80c32705f43d.xml, umdf.iwdfdevice_getdefaultioqueue, wdf.iwdfdevice_getdefaultioqueue, wudfddi/IWDFDevice::GetDefaultIoQueue
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFDevice::GetDefaultIoQueue
 - wudfddi/IWDFDevice::GetDefaultIoQueue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDevice::GetDefaultIoQueue
---

# IWDFDevice::GetDefaultIoQueue


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDefaultIoQueue</b> method retrieves the interface of the default I/O queue for a device.

## -parameters

### -param ppWdfIoQueue 

[out]
A pointer to a variable that receives a pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a> interface for the default I/O queue object.

## -remarks

For more information about queue objects, see <a href="/windows-hardware/drivers/wdf/framework-i-o-queue-object">Framework I/O Queue Object</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>

