---
UID: NF:wudfddi.IPnpCallbackHardware.OnPrepareHardware
title: IPnpCallbackHardware::OnPrepareHardware method
author: windows-driver-content
description: The OnPrepareHardware method notifies a driver to make the specified hardware accessible.
old-location: wdf\ipnpcallbackhardware_onpreparehardware.htm
old-project: wdf
ms.assetid: c821231a-446d-45dd-9c12-9ab05aeb1108
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, ., :, C, H, I, IPnpCallbackHardware, IPnpCallbackHardware interface, OnPrepareHardware method, IPnpCallbackHardware::OnPrepareHardware, O, OnPrepareHardware method, OnPrepareHardware method, IPnpCallbackHardware interface, OnPrepareHardware,IPnpCallbackHardware.OnPrepareHardware, P, UMDFDeviceObjectRef_3b9db069-02f0-4d3e-855d-835bb1bb6d2d.xml, a, b, c, d, e, k, l, n, p, r, umdf.ipnpcallbackhardware_onpreparehardware, w, wdf.ipnpcallbackhardware_onpreparehardware, wudfddi/IPnpCallbackHardware::OnPrepareHardware"
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
-	IPnpCallbackHardware.OnPrepareHardware
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IPnpCallbackHardware::OnPrepareHardware method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnPrepareHardware</b> method notifies a driver to make the specified hardware accessible.


## -syntax


````
HRESULT OnPrepareHardware(
  [in] IWDFDevice *pWdfDevice
);
````


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a> interface for the device object of the device to make accessible.


## -returns



<b>OnPrepareHardware</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes defined in Winerror.h. Do not return HRESULT_FROM_NT(STATUS_NOT_SUPPORTED).

If <b>OnPrepareHardware</b> returns an error code, the framework will still call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556768">IPnpCallbackHardware::OnReleaseHardware</a> method. The <b>OnReleaseHardware</b> method can then free resources that were allocated during the call to <b>OnPrepareHardware</b>. Because <b>OnReleaseHardware</b> must free resources for both success and failure cases of <b>OnPrepareHardware</b>,  it must be able to handle the cleanup of partial resources. 



This method must use the HRESULT_FROM_NT macro to return a specific HRESULT value to  return status to a kernel-mode client. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-kernel-mode-clients-in-umdf-1-x-drivers">Supporting Kernel-mode Clients</a>.




## -remarks



A driver registers the <a href="..\wudfddi\nn-wudfddi-ipnpcallbackhardware.md">IPnpCallbackHardware</a> interface when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create a device object. 

Receiving a call to the <b>OnPrepareHardware</b> method is equivalent to a Microsoft Windows Driver Model (WDM) driver receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> IRP.

For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/finding-and-mapping-hardware-resources-in-umdf-1-x-drivers">Finding and Mapping Hardware Resources in a UMDF Driver</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>



<a href="..\wudfddi\nn-wudfddi-ipnpcallbackhardware.md">IPnpCallbackHardware</a>



<a href="https://msdn.microsoft.com/830D706A-016C-4637-829F-2014AD1A1309">IPnpCallbackHardware2::OnPrepareHardware</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556768">IPnpCallbackHardware::OnReleaseHardware</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IPnpCallbackHardware::OnPrepareHardware method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

