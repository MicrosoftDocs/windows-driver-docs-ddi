---
UID: NF:wudfddi.IPnpCallback.OnQueryStop
title: IPnpCallback::OnQueryStop method
author: windows-driver-content
description: The OnQueryStop method notifies a driver before a device is stopped.
old-location: wdf\ipnpcallback_onquerystop.htm
old-project: wdf
ms.assetid: e0cb14fa-82d0-4ce3-8672-801e7f04d522
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: OnQueryStop method, IPnpCallback::OnQueryStop, OnQueryStop, OnQueryStop method, IPnpCallback interface, wdf.ipnpcallback_onquerystop, wudfddi/IPnpCallback::OnQueryStop, UMDFDeviceObjectRef_9215c39e-2cb9-4de6-9fb3-f228dad51f6d.xml, umdf.ipnpcallback_onquerystop, IPnpCallback, IPnpCallback interface, OnQueryStop method
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
-	IPnpCallback.OnQueryStop
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IPnpCallback::OnQueryStop method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnQueryStop</b> method notifies a driver before a device is stopped. 


## -syntax


````
HRESULT OnQueryStop(
  [in] IWDFDevice *pWdfDevice
);
````


## -parameters




#### - pWdfDevice [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a> interface for the device object of the device that will be stopped.


## -returns


If the driver determines that the device can be stopped, the <b>OnQueryStop</b> callback method must return S_OK or another status code for which SUCCEEDED(status) equals <b>TRUE</b>. Otherwise it must return a status code for which SUCCEEDED(status) equals <b>FALSE</b>.   HRESULT error codes are defined in Winerror.h. Do not return HRESULT_FROM_NT(STATUS_NOT_SUPPORTED).

This method must use the HRESULT_FROM_NT macro to return a specific HRESULT value to  return status to a kernel-mode client. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-kernel-mode-clients-in-umdf-1-x-drivers">Supporting Kernel-mode Clients</a>.



## -remarks


A driver registers the <a href="..\wudfddi\nn-wudfddi-ipnpcallback.md">IPnpCallback</a> interface when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create a device object. 

The framework does not synchronize the <b>OnQueryStop</b> callback function with other PnP and power management callback functions.  

<b>OnQueryStop</b> is not called in framework versions 1.7 and earlier.

For more information about the <b>OnQueryStop</b> callback method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/the-pnp-manager-redistributes-system-resources">The PnP Manager Redistributes System Resources</a>.



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>

<a href="..\wudfddi\nn-wudfddi-ipnpcallback.md">IPnpCallback</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IPnpCallback::OnQueryStop method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

