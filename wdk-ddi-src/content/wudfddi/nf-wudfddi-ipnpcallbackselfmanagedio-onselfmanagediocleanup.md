---
UID: NF:wudfddi.IPnpCallbackSelfManagedIo.OnSelfManagedIoCleanup
title: IPnpCallbackSelfManagedIo::OnSelfManagedIoCleanup method
author: windows-driver-content
description: The OnSelfManagedIoCleanup method releases memory for a device's self-managed I/O operations, after the device is removed.
old-location: wdf\ipnpcallbackselfmanagedio_onselfmanagediocleanup.htm
old-project: wdf
ms.assetid: 0890c352-8722-4108-9b76-60c81179b46b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPnpCallbackSelfManagedIo, IPnpCallbackSelfManagedIo interface, OnSelfManagedIoCleanup method, IPnpCallbackSelfManagedIo::OnSelfManagedIoCleanup, OnSelfManagedIoCleanup method, OnSelfManagedIoCleanup method, IPnpCallbackSelfManagedIo interface, OnSelfManagedIoCleanup,IPnpCallbackSelfManagedIo.OnSelfManagedIoCleanup, UMDFDeviceObjectRef_32b2f920-2288-4d12-8ecd-a5ea61cc8ebd.xml, umdf.ipnpcallbackselfmanagedio_onselfmanagediocleanup, wdf.ipnpcallbackselfmanagedio_onselfmanagediocleanup, wudfddi/IPnpCallbackSelfManagedIo::OnSelfManagedIoCleanup
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
-	IPnpCallbackSelfManagedIo.OnSelfManagedIoCleanup
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IPnpCallbackSelfManagedIo::OnSelfManagedIoCleanup method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnSelfManagedIoCleanup</b> method releases memory for a device's self-managed I/O operations, after the device is removed.


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a> interface for the device object of the device that the driver performs cleanup for.


## -returns



None




## -remarks



A driver registers the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556776">IPnpCallbackSelfManagedIo</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create a device object. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556776">IPnpCallbackSelfManagedIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>
 

 

