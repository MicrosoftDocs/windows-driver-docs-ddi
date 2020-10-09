---
UID: NF:wudfddi.IPnpCallbackSelfManagedIo.OnSelfManagedIoFlush
title: IPnpCallbackSelfManagedIo::OnSelfManagedIoFlush (wudfddi.h)
description: The OnSelfManagedIoFlush method flushes the device for a device's self-managed I/O operations.
old-location: wdf\ipnpcallbackselfmanagedio_onselfmanagedioflush.htm
tech.root: wdf
ms.assetid: dee0e30b-ad03-43e4-8a0c-07d3782d7857
ms.date: 02/26/2018
keywords: ["IPnpCallbackSelfManagedIo::OnSelfManagedIoFlush"]
ms.keywords: IPnpCallbackSelfManagedIo interface,OnSelfManagedIoFlush method, IPnpCallbackSelfManagedIo.OnSelfManagedIoFlush, IPnpCallbackSelfManagedIo::OnSelfManagedIoFlush, OnSelfManagedIoFlush, OnSelfManagedIoFlush method, OnSelfManagedIoFlush method,IPnpCallbackSelfManagedIo interface, UMDFDeviceObjectRef_ddf0d0a2-a913-4e15-b482-16cae945c4a2.xml, umdf.ipnpcallbackselfmanagedio_onselfmanagedioflush, wdf.ipnpcallbackselfmanagedio_onselfmanagedioflush, wudfddi/IPnpCallbackSelfManagedIo::OnSelfManagedIoFlush
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPnpCallbackSelfManagedIo::OnSelfManagedIoFlush
 - wudfddi/IPnpCallbackSelfManagedIo::OnSelfManagedIoFlush
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IPnpCallbackSelfManagedIo.OnSelfManagedIoFlush
---

# IPnpCallbackSelfManagedIo::OnSelfManagedIoFlush


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnSelfManagedIoFlush</b> method flushes the device for a device's self-managed I/O operations.

## -parameters

### -param pWdfDevice 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a> interface for the device object of the device that is flushed.

## -remarks

A driver registers the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackselfmanagedio">IPnpCallbackSelfManagedIo</a> interface when the driver calls the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create a device object.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackselfmanagedio">IPnpCallbackSelfManagedIo</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>