---
UID: NF:wudfddi.IPnpCallbackSelfManagedIo.OnSelfManagedIoFlush
title: IPnpCallbackSelfManagedIo::OnSelfManagedIoFlush method
author: windows-driver-content
description: The OnSelfManagedIoFlush method flushes the device for a device's self-managed I/O operations.
old-location: wdf\ipnpcallbackselfmanagedio_onselfmanagedioflush.htm
old-project: wdf
ms.assetid: dee0e30b-ad03-43e4-8a0c-07d3782d7857
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: UMDFDeviceObjectRef_ddf0d0a2-a913-4e15-b482-16cae945c4a2.xml, wdf.ipnpcallbackselfmanagedio_onselfmanagedioflush, umdf.ipnpcallbackselfmanagedio_onselfmanagedioflush, OnSelfManagedIoFlush method, IPnpCallbackSelfManagedIo interface, IPnpCallbackSelfManagedIo interface, OnSelfManagedIoFlush method, OnSelfManagedIoFlush method, wudfddi/IPnpCallbackSelfManagedIo::OnSelfManagedIoFlush, IPnpCallbackSelfManagedIo, OnSelfManagedIoFlush, IPnpCallbackSelfManagedIo::OnSelfManagedIoFlush
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
req.lib: wudfddi.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Wudfddi.h
apiname:
-	IPnpCallbackSelfManagedIo.OnSelfManagedIoFlush
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IPnpCallbackSelfManagedIo::OnSelfManagedIoFlush method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnSelfManagedIoFlush</b> method flushes the device for a device's self-managed I/O operations.


## -syntax


````
void OnSelfManagedIoFlush(
  [in] IWDFDevice *pWdfDevice
);
````


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a> interface for the device object of the device that is flushed.


## -returns



None




## -remarks



A driver registers the <a href="..\wudfddi\nn-wudfddi-ipnpcallbackselfmanagedio.md">IPnpCallbackSelfManagedIo</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create a device object. 




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IPnpCallbackSelfManagedIo::OnSelfManagedIoFlush method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

