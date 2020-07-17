---
UID: NF:wudfddi.IPnpCallback.OnQueryStop
title: IPnpCallback::OnQueryStop (wudfddi.h)
description: The OnQueryStop method notifies a driver before a device is stopped.
old-location: wdf\ipnpcallback_onquerystop.htm
tech.root: wdf
ms.assetid: e0cb14fa-82d0-4ce3-8672-801e7f04d522
ms.date: 02/26/2018
keywords: ["IPnpCallback::OnQueryStop"]
ms.keywords: IPnpCallback interface,OnQueryStop method, IPnpCallback.OnQueryStop, IPnpCallback::OnQueryStop, OnQueryStop, OnQueryStop method, OnQueryStop method,IPnpCallback interface, UMDFDeviceObjectRef_9215c39e-2cb9-4de6-9fb3-f228dad51f6d.xml, umdf.ipnpcallback_onquerystop, wdf.ipnpcallback_onquerystop, wudfddi/IPnpCallback::OnQueryStop
f1_keywords:
 - "wudfddi/IPnpCallback.OnQueryStop"
 - "IPnpCallback.OnQueryStop"
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
- IPnpCallback.OnQueryStop
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPnpCallback::OnQueryStop


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnQueryStop</b> method notifies a driver before a device is stopped. 


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a> interface for the device object of the device that will be stopped.


## -returns



If the driver determines that the device can be stopped, the <b>OnQueryStop</b> callback method must return S_OK or another status code for which SUCCEEDED(status) equals <b>TRUE</b>. Otherwise it must return a status code for which SUCCEEDED(status) equals <b>FALSE</b>.   HRESULT error codes are defined in Winerror.h. Do not return HRESULT_FROM_NT(STATUS_NOT_SUPPORTED).

This method must use the HRESULT_FROM_NT macro to return a specific HRESULT value to  return status to a kernel-mode client. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-kernel-mode-clients-in-umdf-1-x-drivers">Supporting Kernel-mode Clients</a>.




## -remarks



A driver registers the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallback">IPnpCallback</a> interface when it calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create a device object. 

The framework does not synchronize the <b>OnQueryStop</b> callback function with other PnP and power management callback functions.  

<b>OnQueryStop</b> is not called in framework versions 1.7 and earlier.

For more information about the <b>OnQueryStop</b> callback method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/the-pnp-manager-redistributes-system-resources">The PnP Manager Redistributes System Resources</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallback">IPnpCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>
 

 

