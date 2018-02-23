---
UID: NF:wudfddi.IPnpCallbackSelfManagedIo.OnSelfManagedIoSuspend
title: IPnpCallbackSelfManagedIo::OnSelfManagedIoSuspend method
author: windows-driver-content
description: The OnSelfManagedIoSuspend method suspends a device's self-managed I/O operations.
old-location: wdf\ipnpcallbackselfmanagedio_onselfmanagediosuspend.htm
old-project: wdf
ms.assetid: 7ec30c51-5e07-496b-96af-8eafb564d98d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: UMDFDeviceObjectRef_87fc0596-4d08-4c55-88b0-e2ad9d085745.xml, IPnpCallbackSelfManagedIo, OnSelfManagedIoSuspend, OnSelfManagedIoSuspend method, wdf.ipnpcallbackselfmanagedio_onselfmanagediosuspend, IPnpCallbackSelfManagedIo::OnSelfManagedIoSuspend, umdf.ipnpcallbackselfmanagedio_onselfmanagediosuspend, wudfddi/IPnpCallbackSelfManagedIo::OnSelfManagedIoSuspend, IPnpCallbackSelfManagedIo interface, OnSelfManagedIoSuspend method, OnSelfManagedIoSuspend method, IPnpCallbackSelfManagedIo interface
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
-	IPnpCallbackSelfManagedIo.OnSelfManagedIoSuspend
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IPnpCallbackSelfManagedIo::OnSelfManagedIoSuspend method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnSelfManagedIoSuspend</b> method suspends a device's self-managed I/O operations.


## -syntax


````
HRESULT OnSelfManagedIoSuspend(
  [in] IWDFDevice *pWdfDevice
);
````


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a> interface for the device object of the device for which the self-managed I/O operations are suspended.


## -returns



If the <b>OnSelfManagedIoSuspend</b> callback encounters no errors, it must return
        S_OK or another status code for which SUCCEEDED(status) equals <b>TRUE</b>.

  If it returns a status code for which SUCCEEDED(status) equals <b>FALSE</b>, the framework will stop the device and unload the device's drivers. In this case, the framework  calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556783">IPnpCallbackSelfManagedIo::OnSelfManagedIoFlush</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff556780">IPnpCallbackSelfManagedIo::OnSelfManagedIoCleanup</a> callback methods.

HRESULT error codes are defined in Winerror.h. 




## -remarks



A driver registers the <a href="..\wudfddi\nn-wudfddi-ipnpcallbackselfmanagedio.md">IPnpCallbackSelfManagedIo</a> interface when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create a device object. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>



<a href="..\wudfddi\nn-wudfddi-ipnpcallbackselfmanagedio.md">IPnpCallbackSelfManagedIo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IPnpCallbackSelfManagedIo::OnSelfManagedIoSuspend method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

