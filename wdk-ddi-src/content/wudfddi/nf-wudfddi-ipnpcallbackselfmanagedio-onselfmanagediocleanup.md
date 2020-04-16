---
UID: NF:wudfddi.IPnpCallbackSelfManagedIo.OnSelfManagedIoCleanup
title: IPnpCallbackSelfManagedIo::OnSelfManagedIoCleanup (wudfddi.h)
description: The OnSelfManagedIoCleanup method releases memory for a device's self-managed I/O operations, after the device is removed.
old-location: wdf\ipnpcallbackselfmanagedio_onselfmanagediocleanup.htm
tech.root: wdf
ms.assetid: 0890c352-8722-4108-9b76-60c81179b46b
ms.date: 02/26/2018
keywords: ["IPnpCallbackSelfManagedIo::OnSelfManagedIoCleanup"]
ms.keywords: IPnpCallbackSelfManagedIo interface,OnSelfManagedIoCleanup method, IPnpCallbackSelfManagedIo.OnSelfManagedIoCleanup, IPnpCallbackSelfManagedIo::OnSelfManagedIoCleanup, OnSelfManagedIoCleanup, OnSelfManagedIoCleanup method, OnSelfManagedIoCleanup method,IPnpCallbackSelfManagedIo interface, UMDFDeviceObjectRef_32b2f920-2288-4d12-8ecd-a5ea61cc8ebd.xml, umdf.ipnpcallbackselfmanagedio_onselfmanagediocleanup, wdf.ipnpcallbackselfmanagedio_onselfmanagediocleanup, wudfddi/IPnpCallbackSelfManagedIo::OnSelfManagedIoCleanup
f1_keywords:
 - "wudfddi/IPnpCallbackSelfManagedIo.OnSelfManagedIoCleanup"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wudfddi.h
api_name:
- IPnpCallbackSelfManagedIo.OnSelfManagedIoCleanup
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPnpCallbackSelfManagedIo::OnSelfManagedIoCleanup


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnSelfManagedIoCleanup</b> method releases memory for a device's self-managed I/O operations, after the device is removed.


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a> interface for the device object of the device that the driver performs cleanup for.


## -remarks



A driver registers the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackselfmanagedio">IPnpCallbackSelfManagedIo</a> interface when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create a device object. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackselfmanagedio">IPnpCallbackSelfManagedIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>
 

 

