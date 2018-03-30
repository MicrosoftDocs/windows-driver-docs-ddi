---
UID: NF:wudfddi.IPnpCallbackHardware.OnPrepareHardware
title: IPnpCallbackHardware::OnPrepareHardware method
author: windows-driver-content
description: The OnPrepareHardware method notifies a driver to make the specified hardware accessible.
old-location: wdf\ipnpcallbackhardware_onpreparehardware.htm
old-project: wdf
ms.assetid: c821231a-446d-45dd-9c12-9ab05aeb1108
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPnpCallbackHardware, IPnpCallbackHardware interface, OnPrepareHardware method, IPnpCallbackHardware::OnPrepareHardware, OnPrepareHardware method, OnPrepareHardware method, IPnpCallbackHardware interface, OnPrepareHardware,IPnpCallbackHardware.OnPrepareHardware, UMDFDeviceObjectRef_3b9db069-02f0-4d3e-855d-835bb1bb6d2d.xml, umdf.ipnpcallbackhardware_onpreparehardware, wdf.ipnpcallbackhardware_onpreparehardware, wudfddi/IPnpCallbackHardware::OnPrepareHardware
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


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a> interface for the device object of the device to make accessible.


## -returns



<b>OnPrepareHardware</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes defined in Winerror.h. Do not return HRESULT_FROM_NT(STATUS_NOT_SUPPORTED).

If <b>OnPrepareHardware</b> returns an error code, the framework will still call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556768">IPnpCallbackHardware::OnReleaseHardware</a> method. The <b>OnReleaseHardware</b> method can then free resources that were allocated during the call to <b>OnPrepareHardware</b>. Because <b>OnReleaseHardware</b> must free resources for both success and failure cases of <b>OnPrepareHardware</b>,  it must be able to handle the cleanup of partial resources. 



This method must use the HRESULT_FROM_NT macro to return a specific HRESULT value to  return status to a kernel-mode client. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-kernel-mode-clients-in-umdf-1-x-drivers">Supporting Kernel-mode Clients</a>.




## -remarks



A driver registers the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556764">IPnpCallbackHardware</a> interface when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create a device object. 

Receiving a call to the <b>OnPrepareHardware</b> method is equivalent to a Microsoft Windows Driver Model (WDM) driver receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> IRP.

For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/finding-and-mapping-hardware-resources-in-umdf-1-x-drivers">Finding and Mapping Hardware Resources in a UMDF Driver</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556764">IPnpCallbackHardware</a>



<a href="https://msdn.microsoft.com/830D706A-016C-4637-829F-2014AD1A1309">IPnpCallbackHardware2::OnPrepareHardware</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556768">IPnpCallbackHardware::OnReleaseHardware</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>
 

 

